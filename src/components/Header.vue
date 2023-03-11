<template>
  <div class="bg-light py-3 px-4 w-100 rounded-3 shadow mb-5 ">
    <div class="row align-items-center">
      <div class="col">
        <router-link to="/" class="text-decoration-none fw-bold text-dark fs-2">Home</router-link>
      </div>
      <div class="col-auto">
        <router-link v-if="getUsername().length" to="/dashboard" class="fw-bold btn-link text-dark fs-5 me-3">Dashboard</router-link>
        <router-link v-if="!getUsername().length" to="/login" class="fw-bold btn-link text-dark fs-5">Login</router-link>
        <router-link v-else @click="resetState()" to="/" class="fw-bold btn-link text-dark fs-5">Logout</router-link>
      </div>
    </div>
  </div>
</template>

<script>
  import {  GET_USERNAME, SET_AUTHENTICATION, SET_USERNAME } from "../stores/storeconstants";
  export default{
    methods: {
      getUsername() {
        return this.$store.getters[`auth/${GET_USERNAME}`];
      },
      resetState() {
        this.$store.commit(`auth/${SET_AUTHENTICATION}`, false);
        this.$store.commit(`auth/${SET_USERNAME}`, "");
        this.$router.push("/");
      }
    },
  }
</script>
