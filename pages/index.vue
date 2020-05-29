<template>
  <div>
    	<body>
			<section id="three" class="wrapper">
				<div class="inner flex flex-3">
					<ArticleItem v-for="item in articles" :key="item._id" :title="item.title" :urlArticle="item.urlArticle" :date="item.date" :resume="item.resume" :category="item.category" :id="item._id" :numberLikes="item.vote.positive" @clickLike="addLikes(item)" :numberDislikes="item.vote.negative" @clickDislike="addDislikes(item)">

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
			articles:[]
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
    async addDislikes(item){
    let vote={
      negative: item.vote.negative++
    }
    const response = await this.$axios.put(`https://apimeneame.herokuapp.com/articles/${item._id}`, vote );

    }
  }
}
</script>
