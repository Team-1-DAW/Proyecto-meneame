<template>
  <div>
    <div class="flex-item box">
						<div class="image fit">
							<!-- <img :src='"("+ img +")"' alt="" /> -->
						</div>
						<div class="content">
							<!-- <nuxt-link :to='"/article/("+ id +")"'>{{title}}</nuxt-link > -->
              <h1>{{title}}</h1>
              <p>{{category}}</p>
							<p>{{resume}}</p>
              <p>{{date}}</p>
              <a :href="urlArticle">Ir a la noticia</a>
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
  props: ["title", "urlArticle","date","resume","category", "numberLikes","numberDislikes"],
  methods:{
    likes(){
      this.$emit("clickLike")
    },
    dislikes(){
      this.$emit("clickDislike")
    }
  }
}
</script>
