<template>
   <div class="container">
    <ul>
        <li>
            <img :src="`http://image.tmdb.org/t/p/w342/${filmDescription.poster_path}`"> 
            <h1>{{filmDescription.title}}</h1>
            <h2>{{filmDescription.original_title}}</h2>
            <h3><lang-flag :iso="filmDescription.original_language"/></h3>
            <font-awesome-icon v-for="i in starsAverageCalc(filmDescription.vote_average)" :key="i" icon="fa-solid fa-star" />
            
        </li>
    </ul>
   </div>



</template>

<script>
import LangFlag from "vue-lang-code-flags";
export default {
  name: 'MyCard',
  componets: {
    LangFlag
  },
  
  props: {
    filmDescription: Object
  
  },
  methods: {
        starsAverageCalc (vote){
          let calc =  parseInt(Math.round(vote / 2));
          console.log(calc)
            return   calc; 
        }
    }



}


  



</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

li {
  display: inline-block;
  margin: 15px;
}
.fa-star{
    color: yellow;
}

</style>