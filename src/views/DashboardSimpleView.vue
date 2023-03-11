<template>
  <div class="my-5">
    <div class="container">
      <h1>Welcome to dashboard</h1>
    </div>
    
  </div>
</template>

<script>
  import { GET_USERNAME } from "../stores/storeconstants";

  export default {
    data(){
      
    },
    mounted() {
      if(!this.$store.getters[`auth/${GET_USERNAME}`].length){
        this.$router.push("/");
      }
      
    },
  }
</script> 