<template>
    <div class="user-update">
        <h2>Update user</h2>
        <input type="text" v-model="name" /> <br />
        <input type="text" v-model="job" /> <br />

        <button @click="updateUser">Update</button>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            name: '',
            job: ''

        }
    },

    methods: {
        async updateUser() {
            try {
                const user = await axios.put(
                    "https://reqres.in/api/users/2",
                    {
                        name: this.name,
                        job: this.job,
                    }
                );

                console.log(user);
                alert("User updated!");
            } catch (e) {
                console.log(e);
            }
        }
    },
}
</script>