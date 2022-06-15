<template>
  
    <div>
        <section id="searchbar"><input type="text" placeholder="search" v-model="ricercaUtente"> <button @click="searchFilm">cerca</button></section>
        <MyCard
        v-for="(element, i) in listaFilm" :key="i" :filmDescription="element"
        />

    </div>


</template>

<script>
    import axios from 'axios'
    import MyCard from './MyCard.vue';
    export default {
    name: "MyFilm",
    data() {
        return {
            apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=573c6074892e33f67b46537c63bfbe2c&language=it-IT&query=a",
            apiUrlTv:"https://api.themoviedb.org/3/search/tv?api_key=573c6074892e33f67b46537c63bfbe2c&language=it-IT&query=a",
            ListaSerie: [],
            listaFilm: [],
            ricercaUtente: ""
        };
    },
    created() {
        axios.get(this.apiUrl)
            .then(result => {
            this.listaFilm = result.data.results;
            console.log(result);
        });
    },
    components: { 
        MyCard 
        },
    
    methods: {
        searchSeries() {
            console.log(this.ricercaUtente);
            this.apiUrlTv= "https://api.themoviedb.org/3/search/tv?api_key=573c6074892e33f67b46537c63bfbe2c&language=it-IT&query=" + this.ricercaUtente;
            console.log(this.apiUrlTv);
            axios.get(this.apiUrlTv)
            .then(result => {
            this.ListaSerie = result.data.results;
            console.log(result);
            });
            
        },
        searchFilm() {
            console.log(this.ricercaUtente);
            this.apiUrl= "https://api.themoviedb.org/3/search/movie?api_key=573c6074892e33f67b46537c63bfbe2c&language=it-IT&query=" + this.ricercaUtente;
            console.log(this.apiUrl);
            axios.get(this.apiUrl)
            .then(result => {
            this.listaFilm = result.data.results;
            console.log(this.ListaSerie);
            });
             this.searchSeries();
            
        },
        
    }
}
    





</script>

<style scoped lang="scss">

</style>