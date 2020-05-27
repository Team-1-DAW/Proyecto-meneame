<template>
  <div>
    <MainNav/>
    <nuxt />
    <MainFooter/>
  </div>
</template>
<script>
import MainNav from '@/components/MainNav'
import MainFooter from '@/components/MainFooter'

export default {
  name:"index",
  data(){
    return{

    }
    },
    components:{
      MainNav,
      MainFooter
  }
}

</script>
