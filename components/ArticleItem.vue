<template>
  <div>
    <div class="flex-item box">
						<div class="image fit">
							<!-- <img :src='"("+ img +")"' alt="" /> -->
						</div>
						<div class="content">
							<nuxt-link to="/article/">{{title}}</nuxt-link to="/article/">
              <p>{{category}}</p>
							<p>{{resume}}</p>
              <p>{{date}}</p>
              <p>{{urlArticle}}</p>
						</div>
            <button @click.prevent="likes" class="button small">{{numberLikes}}</button>
            <button @click.prevent="dislikes" class="button special small">{{numberDislikes}}</button>
					</div>
  </div>
</template>
<script>
export default {
  name:"Article",
  data(){
    return{
      numberLikes: 0,
      numberDislikes: 0
    }
  },
  props: ["title", "urlArticle","date","resume","category"],
  methods:{
    likes(){
      this.numberLikes ++
    },
    dislikes(){
      this.numberDislikes ++
    }
  },
  /* computed:{
    numberLikes(){

    }
  } */
}
</script>
