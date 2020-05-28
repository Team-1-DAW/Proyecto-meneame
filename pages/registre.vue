<template>
  <div>
    <div>
    <label for="name">Name</label><br>
    <input type="text" placeholder="Name" v-model="name"><br>
    </div>
    <div>
    <label for="surname">Surname</label><br>
    <input type="text" placeholder="Surname" v-model="surname"><br>
    </div>
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
      password:"",
      name:"",
      surname:""
    }
  },
  methods:{
     async registre(){
      let userData={
        email: this.email,
        password: this.password,
        name: this.name,
        surname: this.surname
      }
      const addUser = await this.$axios.post('/users', userData)
      this.$router.push('/')

    }
  }
}
</script>
