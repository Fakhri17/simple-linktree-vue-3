<template>
  <div class="bg-custom py-5">
    <div class="container">
      <div class="mobile-view">
        <Header />
        <div class="text-white mb-3">
          <h2 class="mb-3">Dashboard Menu</h2>
          <h5 class="mb-3">Welcome {{ username }}</h5>
        </div>
        <div class="card mb-4">
          <div class="card-body">
            <h3 class="mb-3">Form menu</h3>
            <form>
              <div class="mb-3">
                <div v-for="item in formInput" :key="item" class="mb-3">
                  <label :for="`input${item.label}`" class="form-label fw-semibold">{{ item.label }}</label>
                  <input :type="item.type" class="form-control" :id="`input${item.label}`" :placeholder="item.placeholder" :value="item.value">
                </div>
                <button type="submit" class="btn btn-dark rounded w-100 my-3">Submit</button>
              </div>
            </form>
          </div>
        </div>
        <Footer />
      </div>
    </div>
  </div>
  
</template>

<script>
  
  import Header from "../components/Header.vue";
  import Footer from "../components/Footer.vue";
  export default {
    components: {
      Header,
      Footer
    },
    data(){
      return{
        username: localStorage.getItem("username"),
      }
    },
    setup() {
      const formInput = [
        {
          id: 1,
          label: "Username",
          type: "text",
          placeholder: "Username",
          value: "@fakhri17",
        },
        {
          id: 2,
          label: "Email",
          type: "email",
          placeholder: "Email",
          value: "fakhricoffe@gmail.com",
        },
        {
          id: 3,
          label: "Instagram",
          type: "text",
          placeholder: "Instagram",
          value: "https://www.instagram.com/fakhriii_15/",
        },
        {
          id: 4,
          label: "Twitter",
          type: "text",
          placeholder: "Twitter",
          value: "https://twitter.com/fakhriii_15",
        },
        {
          id: 5,
          label: "Facebook",
          type: "text",
          placeholder: "Instagram",
          value: "https://www.facebook.com/FakhriAL17/",
        },
        {
          id: 6,
          label: "Tiktok",
          type: "text",
          placeholder: "Tiktok",
          value: "https://www.tiktok.com/@fakhriii_15",
        },
      ]
      return {
        formInput
      }
    },
    mounted(){
      if(localStorage.getItem("username") == null){
        this.$router.push("/login");
      }
    }
  }
</script>

