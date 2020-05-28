<template>
  <div>
    	<header id="header">
				<nav class="left">
					<a href="#menu"><span>Menu</span></a>
				</nav>
				<button class="button alt small fit"><nuxt-link to="/">Meneame</nuxt-link></button>
				<nav class="right">
					<button class="button alt small fit"><nuxt-link to="/login">Login</nuxt-link></button>
          			<button class="button alt small fit"><nuxt-link to="/registre">Sing Up</nuxt-link></button>
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
  name:"MainNav"
}
</script>
