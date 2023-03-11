<template>
   <div class="bg-custom">
    <div class="container">
      <div class="mobile-view">
        <div class="d-flex flex-column min-vh-100 justify-content-center align-items-center">
          <div class="alert alert-danger" role="alert">
            Karena Ini masih proses isi data dengan bebas untuk validasi
          </div>
          <div class="card shadow px-1" style="width: 350px;">
            <div class="card-body">
              <h4 class="text-center mb-4">LOGIN MENU</h4>
              <!-- <h5 class="mb-4">Sign in</h5> -->
              <form name="login-form" class="my-4">
                <div class="mb-3">
                  <input type="text" class="form-control w-100" placeholder="Username" v-model="input.username">
                </div>
                <div class="mb-3">
                  <input type="password" class="form-control" placeholder="Password" v-model="input.password">
                </div>
                <button type="submit" class="btn btn-dark px-4 py-2 w-100" v-on:click.prevent = "login()">Login</button>
              </form>
              <div class="text-center mb-4">
                <h5 class="text-danger">{{ output }}</h5>
              </div>
              <div class="text-center mb-4">
                <router-link class="text-dark text-center" to="/">Back To Home</router-link>   
              </div>   
            </div>
          </div>
        </div>
      </div>
    </div>
    
   </div>
</template>

<script>
  import { SET_AUTHENTICATION, SET_USERNAME} from "../stores/storeconstants";
  export default{
    data(){
      return{
        input:{
          username: "",
          password: ""
        },
        output: ""
      }
    },
    methods:{
      login(){
        if(this.input.username != "" && this.input.password != ""){
          // this.output = "Authentication complete"
          //stores true to the set_authentication and username to the set_username 
          this.$store.commit(`auth/${SET_AUTHENTICATION}`, true);
          this.$store.commit(`auth/${SET_USERNAME}`, this.input.username);
          this.output = "Authentication complete."
          this.$router.push("/dashboard");
        }else{
          this.$store.commit(`auth/${SET_AUTHENTICATION}`, false);
          this.output = "Username and password can not be empty"
        }
      }
    }
  }
</script>