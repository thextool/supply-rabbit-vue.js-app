<template>
<div id="Teachers">
    <div>
        <h1>Teachers</h1>
        <form @submit.prevent="addTeacher">
            <label>Name</label>
            <input type="text" v-model="name"/>
            <label>School</label>
            <input type="text" v-model="school"/>
            <label>School Address</label>
            <input type="text" v-model="address"/>
            <button type="submit">Add Information</button>
        </form>

    </div>
    <router-view />
</div>
</template>

<script>
export default {

    name: "Teachers",
    data() {
        return {
            name: "",
            school: "",
            address: ""
        }
    },
    methods: {
        addTeacher(){
            let teacherObject = {
                "name": this.name,
                "school": this.school,
                "address": this.address,
                "email": null,
                "profile_picture": null,
                "logged_in": null
            }
        fetch('https://supply-rabbit-server.herokuapp.com/teachers', {
            method: 'POST',
            headers:{
                'Content-Type': 'application/json'
            },
            body: JSON.stringify(teacherObject)
        })
        .then(response => response.json())
        .then(teachers => location.replace(`http://localhost:8080/#/request=${teachers.teachers.id}`))
        }
    }
};
</script>

<style>
#Teachers {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 10vw;
}
#Teachers h1 {
    color: white;
    font-size: 2.5em;
}
#Teachers form {
    width: 18vw;
    color: white;
    display: flex;
    flex-direction: column;
    background-image: linear-gradient(rgba(0,0,0,0.9), rgba(0,0,0,0.2));
    padding: 2em;
    border-radius: 5%;
}
#Teachers form label, form input {
    margin: 0.5em;
}
form button {
    transition: 0.2s;
    color: white;
    border: 2px solid white;
    font-size: 0.8em;
    text-transform: uppercase;
    margin: 3em;
    background-color: rgba(0,0,0,0)
}
form button:hover {
    cursor: pointer;
    transition: 0.2s;
    background-color: white;
    color: black;
    box-shadow:  inset 0 0 0 3px  white;
}
form button:active {
    background-color: rgba(0, 0, 0, 0);
    box-shadow: none;
    border-style: hidden;
    color: white;
}
</style>
