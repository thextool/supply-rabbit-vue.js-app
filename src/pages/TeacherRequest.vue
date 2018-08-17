<template>
    <div id="TeacherRequest">
            <h1>Request Items</h1>
        <div id="ItemAdd">
            <form @submit.prevent="addItemToCart">
                <label>Item Name</label>
                <input type="text" v-model="supply_name"/>
                <label>Quantity Needed</label>
                <input type="text" v-model="quantity_needed"/>
                <button type="submit">Add Item</button>
            </form>
        <div id="Cart">
            <h1>Cart</h1>
            <ul>
                <li v-for="cartItem in cartItems"
                    v-bind:key="cartItem.id">
                    <span class="cartItem">
                        <p>Item: {{cartItem.supply_name}}</p>
                        <p>Quantity: {{cartItem.quantity_needed}}</p>
                        <button @click="removeCartItem(cartItem)" type="button" id="removeCartItemButton">X</button>
                    </span>
                </li>
            </ul>
            <div id="Request">
                <button @click="submitCart" type="button">Request</button>
            </div>
        </div>
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
            .then(teachers => location.replace('https://supply-rabbit-96c3e.firebaseapp.com/#/donations'))
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
    margin-top: 10vw;
    width: 100vw;
}
#TeacherRequest h1 {
    font-size: 2.5em;
}
#ItemAdd {
    background-color: rgba(0, 0, 0, 0.65);
    padding: 2em;
    border-radius: 5%;
}
label, p, li, ul {
    color: white;
    list-style: none;
}
#Cart h1 {
    font-size: 2em;
}
.cartItem {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
}
#removeCartItemButton {
    transition: 0.3s;
    font-size: 1em;
    color: white;
    opacity: 0.4;
    background-color: rgba(0, 0, 0, 0);
    max-height: 1.5vw;
    border: none;
    box-shadow: none;
}
#removeCartItemButton:hover {
    opacity: 1;
    transform: scale(1.25);
    cursor: pointer;
}
#removeCartItemButton:active {
    box-shadow: none;
}
#Request button {
    transition: 0.2s;
    color: white;
    border: 2px solid white;
    font-size: 0.8em;
    text-transform: uppercase;
    margin: 1em;
    background-color: rgba(0,0,0,0)
}
#Request button:hover {
    cursor: pointer;
    transition: 0.2s;
    background-color: white;
    color: black;
    box-shadow:  inset 0 0 0 3px  white;
}
#Request button:active {
    background-color: rgba(0, 0, 0, 0);
    box-shadow: none;
    border-style: hidden;
    color: white;
}
</style>
