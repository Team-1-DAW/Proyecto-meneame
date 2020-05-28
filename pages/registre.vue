<template>
  <div>
    <div>
    <label for="email">Email</label><br>
    <input type="email" placeholder="example@example.com" v-model="email"><br>
    </div>
    <div>
    <label for="password">Password</label>
    <input type="password" v-model="password"><br>
    </div>
    <button href="#" @click.prevent="registre">Sing up</button>
  </div>
</template>
<script>
export default {
  name:"registre",
  data(){
    return{
      email: "",
      password:""
    }
  },
  methods:{
     async registre(){
      let userData={
        email: this.email,
        password: this.password
      }
      const addUser = await this.$axios.post('http://localhost:8080/users', userData)
      this.$router.push('/')

    }
  }
}
</script>
