<template>
  <div>
    	<body>
			<section id="three" class="wrapper">
				<div class="inner flex flex-3">
					<ArticleItem v-for="item in articles" :key="item._id" :title="item.title" :urlArticle="urlArticle" :date="date" :resume="resume">
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
		const response = await this.$axios.get('/articles');
    this.articles = response.data
	}
}
</script>
