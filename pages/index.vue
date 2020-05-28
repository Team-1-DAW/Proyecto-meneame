<template>
  <div>
    	<body>
			<section id="three" class="wrapper">
				<div class="inner flex flex-3">
					<Article v-for="item in articles" :key="item.id">
					</Article>	
				</div>
			</section>
	</body>
  </div>
</template>
<script>
import Article from '@/components/Article'
export default {
	name: "index",
	data(){
		return{
			articles:[]
		}
	},
	components:{
		Article
	},
	async mounted(){
		const response = await this.$axios.get('http://localhost:8080/articles');
		this.articles = response.data
	}
}
</script>
