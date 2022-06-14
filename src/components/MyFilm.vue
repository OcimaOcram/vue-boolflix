<template>
  
    <div>
        <section id="searchbar"><input type="text" placeholder="search" v-model="ricercaUtente" @searchFilm> <button>cerca</button></section>
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
            apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=573c6074892e33f67b46537c63bfbe2c&language=it-IT&query=ritorno",
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
    components: { MyCard },
    
    methods: {
        searchFilm() {
            console.log(this.ricercaUtente);
        }
    }
}
    





</script>

<style scoped lang="scss">

</style>