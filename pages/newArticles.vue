<template>
    <div>
        <form>
             <label for="Tittle">Tittle</label>
            <input type="text" v-model="title">

            <label for="Resume">Resume:</label>
            <input type="text" v-model="resume">

            <label for="Category">Category:</label>
            <select name="Category" id="Category" v-model="CategorySelected">
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
            CategorySelected:"",
            urlArticle:"",
            date:""

        }
    },
    methods:{
    async addArticle(){
    let newArticle={
        title:this.title,
        resume:this.resume,
        category:this.CategorySelected,
        url:this.urlArticle,
        date:this.date
    }
    const addNewArticle = await this.$axios.post('https://apimeneame.herokuapp.com/articles', newArticle);
    this.$router.push('/')
    }
    }
}
</script>
