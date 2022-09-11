<template>
  <div class="card" id="top">
    <div class="card-header pb-0">
      <h2>USER</h2>
    </div>
    <div class="card-body px-0 pt-0 pb-2">
      <div class="table-responsive p-0">
        <table class="table align-items-center mb-0 text-center">
          <thead>
            <tr>
              <th class="text-uppercase font-weight-bolder opacity-7">Foto</th>
              <th class="text-uppercase font-weight-bolder opacity-7">First Name</th>
              <th class="text-uppercase font-weight-bolder opacity-7">Last Name</th>
              <th class="text-uppercase font-weight-bolder opacity-7">Email</th>
            </tr>
          </thead>
          <tbody v-if="get && get.length">
            <tr v-for="get of get">
              <td>
                <img :src=get.avatar class="avatar avatar-xxl" />
              </td>
              <td>
                <h5 class="font-weight-bold mb-0">{{get.first_name}}</h5>
              </td>
              <td>
                <h5 class="font-weight-bold mb-0">{{get.last_name}}</h5>
              </td>
              <td>
                <h5 class="font-weight-bold mb-0">{{get.email}}</h5>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>



<script>
import axios from 'axios';
export default {
  name: "authors-table",
  data() {
    return {
      get: []
    }
  },
  created() {
    axios.get('https://reqres.in/api/users')
      .then(response => {
        this.get = response.data.data
      })
  }
}
</script> 
