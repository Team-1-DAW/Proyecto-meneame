<template>
  <div>
    <form>

            <label for="email">Email:</label>
            <input type="email" v-model="email">

            <label for="password">Password:</label>
            <input type="password" v-model="password">
            <p><a href="#">Forgot your password?</a>
            <div id="lower">

                <input type="submit" value="Login" @click.prevent="login">
            </div>
        </form>
  </div>
</template>
<script>
export default {
  name: "login",
  data(){
    return{
      email:"",
      password:""
    }
  },
  methods:{
   async login(){
     let userData={
         email: this.email,
          password: this.password
      }
      const addUser = await this.$axios.post('auth/login', userData);
      window.localStorage.setItem("token",addUser.data.token)
      this.$router.push('/')
    }
  }
}
</script>
