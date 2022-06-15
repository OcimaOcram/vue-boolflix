<template>
  
    <div>
        <section id="searchbar"><input type="text" placeholder="search" v-model="ricercaUtente"> <button @click="searchMovie">cerca</button></section>
        <MyCard
        v-for="element in listaFilm" :key="element.i" :filmDescription="element"
        />
        <MySeries  v-for="item in listaSerie" :key="item.index" :seriesDescription="item"/>
        

    </div>


</template>

<script>
    import axios from 'axios'
    import MyCard from './MyCard.vue';
    import MySeries from './MySeries.vue';
    
    export default {
    name: "MyFilm",
    data() {
        return {
            apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=573c6074892e33f67b46537c63bfbe2c&language=it-IT&query=a",
            apiUrlTv:"https://api.themoviedb.org/3/search/tv?api_key=573c6074892e33f67b46537c63bfbe2c&language=it-IT&query=a",
            listaSerie: [],
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
    MyCard,
    MySeries
},
    
    methods: {
    searchMovie() {
      this.apiUrl= "https://api.themoviedb.org/3/search/movie?api_key=573c6074892e33f67b46537c63bfbe2c&language=it-IT&query=" + this.ricercaUtente;
      axios.get(this.apiUrl)
      .then(result => {
          this.listaFilm = result.data.results;
          console.log(result)
      }),
      this.searchSerie()
    },
    searchSerie() {
      this.apiUrlTv= "https://api.themoviedb.org/3/search/tv?api_key=573c6074892e33f67b46537c63bfbe2c&language=it-IT&query=" + this.ricercaUtente;
      axios.get(this.apiUrlTv)
      .then(result => {
          this.listaSerie = result.data.results;
          console.log(result)
      })
    }

  }
}
    





</script>

<style scoped lang="scss">

</style>