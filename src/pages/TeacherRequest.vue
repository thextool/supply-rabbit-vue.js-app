<template>
    <div id="TeacherRequest">
        <div id="ItemAdd">
            <h1>Request Items</h1>
            <form @submit.prevent="addItemToCart">
                <label>Item Name</label>
                <input type="text" v-model="supply_name"/>
                <label>Quantity Needed</label>
                <input type="text" v-model="quantity_needed"/>
                <button type="submit">Add Item</button>
            </form>
        </div>
        <div id="Cart">
            <h1>Cart</h1>
            <ul>
                <li v-for="cartItem in cartItems"
                    v-bind:key="cartItem.id">
                    <span class="cartItem">
                        Item: {{cartItem.supply_name}} | 
                        Quantity: {{cartItem.quantity_needed}}
                        <button @click="removeCartItem(cartItem)" type="button">X</button>
                    </span>
                </li>
            </ul>
        </div>
        <div id="Request">
            <button @click="submitCart" type="button">Request</button>
        </div>
    <router-view />
    </div>
</template>

<script>
export default {
    name: 'TeacherRequest',
    data() {
        return {
            supply_name: "",
            quantity_needed: undefined,
            cartItems: []
        }
    },
    methods: {
        addItemToCart() {
            this.cartItems.push({
                supply_name: this.supply_name,
                quantity_needed: this.quantity_needed
            })
            this.supply_name = "",
            this.quantity_needed = undefined
        },
        removeCartItem(cartItem) {
            const cartItemIndex = this.cartItems.indexOf(cartItem)
            this.cartItems.splice(cartItemIndex, 1)
        },
        submitCart() {
            let params = window.location.href.split('=')[1]
            let supplyObject = {
                    "supply_name": this.cartItems[0].supply_name,
                    "quantity_needed": this.cartItems[0].quantity_needed,
                    "teacher_id": params
                }
            fetch('https://supply-rabbit-server.herokuapp.com/supplies', {
                method: 'POST',
                headers:{
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify(supplyObject)
            })
            .then(response => response.json())
            // .then(response => console.log(response))
            .then(teachers => location.replace('http://localhost:8080/#/donations'))
        }
    }
}
</script>

<style>
#TeacherRequest {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    height: 100vw;
    width: 100vw;
    margin: 0;
    left: 0;
}
label, p, li {
    color: white;
}
</style>
