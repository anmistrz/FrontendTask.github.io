<template>
    <div>
        <button @click="deleteUser()">Delete</button>
    </div>
</template>

<script>
import axios from 'axios';

export default {

    methods: {
        async deleteUser() {
            let x = window.confirm("You want to delete the user?");

            if (x) {
                const user = await axios.delete(
                    "https://reqres.in/api/users/2"
                );

                console.log(user);
                alert("User deleted!");
            }
        },
    },
}
</script>