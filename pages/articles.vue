<template>
    <div>
        <form>
             <label for="Tittle">Tittle</label>
            <input type="text" v-model="title">

            <label for="Resume">Resume:</label>
            <input type="text" v-model="resume">
            
            <label for="Category">Category:</label>
            <input type="text" v-model="category">
               
            <label for="Url">Url:</label>
            <input type="text" v-model="urlArticle">
            
            <label for="Date">Date:</label>
            <input type="date" v-model="date">

                <input type="submit" @click.prevent="addArticle">
        </form>
    </div>    
</template>
<script>
export default {
    name: "articulos",
    data(){
        return{
            title:"",
            resume:"",
            category:"",
            urlArticle:"",
            date:""
            
        }
    },
    methods:{
    async addArticle(){
    let newArticle={
        title:this.title,
        resume:this.resume,
        category:this.category,
        urlArticle:this.urlArticle,    
        date:this.date
    }
    const addNewArticle = await this.$axios.post('http://localhost:8080/articles', newArticle);
    this.$router.push('/')
    }    
    }
}
</script>