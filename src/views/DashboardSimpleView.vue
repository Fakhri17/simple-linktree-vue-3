<template>
  <div class="bg-custom py-5">
    <div class="container">
      <div class="mobile-view">
        <Header />
        <div class="text-white">
          <h2>Welcome to dashboard menu</h2>
        </div>
      </div>
      
    </div>
  </div>
  
</template>

<script>
  
  import Header from "../components/Header.vue";
  export default {
    components: {
      Header,
    },
  }
</script>

