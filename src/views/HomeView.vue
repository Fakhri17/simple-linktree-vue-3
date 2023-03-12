


<template>
  <div class="bg-custom py-5">
    <div class="container">
      <div class="mobile-view">
        <Header />
        <div class="d-flex flex-column align-items-center">
          <div class="mb-4">
            <img class="rounded-circle img-thumbnail img-circle" alt="avatar1" src="https://fakhri.madeit.cool/assets/image/myphoto.jpg" />
          </div>
          <div class="mb-2">
            <h1 class="text-center text-white fs-2">@fakhri17</h1>
          </div>
          <div>
            <h5 class="text-white">Email: fakhricoffe@gmail.com</h5>
          </div>
        </div>
        <div class="d-flex justify-content-center my-3">
          <a v-for="item in sosmed" :key="item" :href="item.link" target="_blank" 
            class="text-white mx-2 animation-icons">
            <i :class="`bi bi-${item.icon} icon-sosmed-1 animation-icons`"></i>
          </a>
        </div>
        <div class="my-4">
          <a v-for="item in sosmed" :key="item" :href="item.link" target="_blank"
            class="btn btn-light button-sosmed-animations w-100 rounded-pill shadow d-flex align-items-center mb-3">
            <i :class="`bi bi-${item.icon} icon-sosmed-1`"></i>
            <div class="mb-1 text-center w-100 h5">{{ item.name }}</div>
          </a>
        </div>
        <Footer />
      </div>
      
    </div>
  </div>
  
</template>

<script>
  import {  GET_USERNAME } from "../stores/storeconstants";
  import Header from "../components/Header.vue";
  import Footer from "../components/Footer.vue";
  export default {
    components: {
      Header,
      Footer
    },
    methods: {
      getUsername() {
        return this.$store.getters[`auth/${GET_USERNAME}`];
      }
    },
    setup() {
      const sosmed = [
        {
          name: 'Instagram',
          icon: 'instagram',
          link: 'https://www.instagram.com/fakhriii_15/'
        },
        {
          name: 'Twitter',
          icon: 'twitter',
          link: 'https://twitter.com/fakhriii_15'
        },
        {
          name: 'Facebook',
          icon: 'facebook',
          link: 'https://www.facebook.com/FakhriAL17/'
        },
        {
          name: 'Tiktok',
          icon: 'tiktok',
          link: 'https://www.tiktok.com/@fakhriii_15'
        }
      ]
      return {
        sosmed,
      }
    }
  }
</script>

