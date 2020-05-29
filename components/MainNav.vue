<template>
  <div>
    	<header id="header">
				<button class="button alt small fit"><nuxt-link to="/">Meneame</nuxt-link></button>
				<nav class="right">

					<button class="log"><nuxt-link to="/login">Login</nuxt-link></button>
          			<button class="log"><nuxt-link to="/registre">Sing Up</nuxt-link></button>
          			<button class="log"><nuxt-link to="/newArticles">Add articles</nuxt-link></button>
                	<button class="log button alt small fit" @click.prevent="logOut">Log out</button>
				</nav>
			</header>
      <nav id="menu">
				<ul class="links">
					<li><nuxt-link to="/" class="logo">Home</nuxt-link></li>
					<li><nuxt-link to="/generic">Generic</nuxt-link></li>
					<li><nuxt-link to="/elements">Elements</nuxt-link></li>
				</ul>
				<ul class="actions vertical">
					<li><nuxt-link to="/login">Login</nuxt-link></li>
				</ul>
			</nav>
  </div>
</template>
<script>
export default {
  name:"MainNav",
  methods:{
    logOut(){
      window.localStorage.removeItem("token");
      alert('se ha cerrado la sesion')
    }
  }
}
</script>
