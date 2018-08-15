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
    border: 2px solid white;
    height: 50vw;
    width: 100vw;
    margin: 0;
    left: 0;
}
h1 {
    color: white;
}
</style>
