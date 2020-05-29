<template>
  <div>
    	<body>
			<section id="" class="wrapper">
        <label for="Category">Category:</label>
            <select name="Category" id="Category" v-model="categorySelected" @change.prevent="changeCurrentCategory">
                <option value="Deporte">Deporte</option>
                <option value="Salud">Salud</option>
                <option value="Politica">Politica</option>
                <option value="Animales">Animales</option>
                <option value="Desarrollo y Multimedia">Desarrollo y Multimedia</option>
                <option value="Anime">Anime</option>
                <option value="Literatura">Literatura</option>
                <option value="Ciencia">Ciencia</option>
                <option value="Musica">Musica</option>
            </select>

				<div class="inner flex flex-3">
					<ArticleItem v-for="item in filteredArticles" :key="item._id" :title="item.title" :urlArticle="item.url" :date="item.date" :resume="item.resume" :category="item.category" :id="item._id" :numberLikes="item.vote.positive" :href="item.url" @clickLike="addLikes(item)" :numberDislikes="item.vote.negative" @clickDislike="addDislikes(item)">

					</ArticleItem>
				</div>
			</section>
	</body>
  </div>
</template>
<script>
import ArticleItem from '@/components/ArticleItem'
export default {
	name: "index",
	data(){
		return{
      articles:[],
      categorySelected:"",
      filteredArticles:[]
		}
	},
	components:{
		ArticleItem
	},
	async mounted(){
		const response = await this.$axios.get('https://apimeneame.herokuapp.com/articles');
    this.articles = response.data
  },
  methods:{
    async addLikes(item){
    let vote={
      positive: item.vote.positive++
    }
    const response = await this.$axios.put(`https://apimeneame.herokuapp.com/articles/${item._id}`, vote );
    },

    // article
    // id, title, content, votes, uid

    // conmments
    // id, message, votes, articleId

    // API

    // [GET] /articles => Devuelve todos los articulos
    // [GET] /articles/:id ==> Devuelve un articulo
    // [GET] /articles/:id/commments => Devuelve todos los comentarios de un artículo


    async addDislikes(item){
    let vote={
      negative: item.vote.negative++
    }
    const response = await this.$axios.put(`https://apimeneame.herokuapp.com/articles/${item._id}`, vote );
    },
    changeCurrentCategory(){
      let articulos = this.articles
      let filtered= articulos.filter(item => item.category === this.categorySelected)
      this.filteredArticles= filtered
      return this.filteredArticles
    }
  }
}
</script>
