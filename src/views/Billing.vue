<template>
  <div class="card mx-4" id="top">
    <div class="card-header pb-0">
      <h2>TAMBAH USER</h2>
    </div>
    <div class="card-body px-3 pt-0 pb-2">
      <div class="mb-3">
      <label for="Email" class="form-label fs-5 text-uppercase font-weight-bolder opacity-7">Email</label>
      <input type="email" class="form-control" id="Email" v-model="email">
      </div>
      <div class="mb-3">
        <label for="Nama" class="form-label fs-5 text-uppercase font-weight-bolder opacity-7">Nama</label>
        <input type="text" class="form-control" id="Nama" v-model="name">
      </div>
      <button @click="post()" class="btn btn-primary">Simpan</button>
      <div id="email"></div>
      <div id="name"></div>
    </div>
  </div>
</template>

<script>
  import axios from 'axios';

  export default{
    data() {
      return{
        email: '',
        name: '',
        errors: []
      }
    },

    methods: {
      post() {
        axios.post('https://reqres.in/api/users', {
          email: this.email,
          name: this.name
        })
        .then(response => {})
        .catch(e => {
          this.errors.push(e)
        })

        document.getElementById('email').innerHTML = '<div class="fs-4">Email : ' + this.email + '</div>'
        document.getElementById('name').innerHTML = '<div class="fs-4">Nama : ' + this.name + '</div>'
    }
  }
}
</script>

<!-- <template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-8">
        <div class="row mt-4">
          <div class="col-xl-6 mb-xl-0 mb-4">
            <master-card />
          </div>
          <div class="col-xl-6">
            <div class="row">
              <div class="col-md-6">
                <default-info-card
                  :classIcon="salary.classIcon"
                  :title="salary.title"
                  :desc="salary.desc"
                  :price="salary.price"
                />
              </div>
              <div class="col-md-6">
                <default-info-card
                  :classIcon="paypal.classIcon"
                  :title="paypal.title"
                  :desc="paypal.desc"
                  :price="paypal.price"
                />
              </div>
            </div>
          </div>
          <div class="col-md-12 mb-4">
            <payment-card />
          </div>
        </div>
      </div>
      <div class="col-lg-4">
        <invoice-card class="mt-4" />
      </div>
    </div>
    <div class="row">
      <div class="col-md-7">
        <billing-card />
      </div>
      <div class="col-md-5">
        <transaction-card />
      </div>
    </div>
  </div>
</template>

<script>
import MasterCard from "@/examples/Cards/MasterCard.vue";
import DefaultInfoCard from "@/examples/Cards/DefaultInfoCard.vue";
import PaymentCard from "./components/PaymentCard.vue";
import InvoiceCard from "./components/InvoiceCard.vue";
import BillingCard from "./components/BillingCard.vue";
import TransactionCard from "./components/TransactionCard.vue";

export default {
  name: "Billing",
  components: {
    MasterCard,
    DefaultInfoCard,
    PaymentCard,
    InvoiceCard,
    BillingCard,
    TransactionCard,
  },
  data() {
    return {
      salary: {
        classIcon: "text-white fas fa-landmark",
        title: "Salary",
        desc: "Belong Interactive",
        price: "+$2000",
      },
      paypal: {
        classIcon: "text-white fab fa-paypal",
        title: "Paypal",
        desc: "Freelance Payment",
        price: "$455.00",
      },
    };
  },
};
</script> -->
