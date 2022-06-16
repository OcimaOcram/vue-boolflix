<template>
   <div class="container">
    <ul>
        <li>
            <div class="poster">
              <img :src="`http://image.tmdb.org/t/p/w342/${seriesDescription.poster_path}`"> 
            </div>
            <div class="descrizioneFilm">
              <h1>{{seriesDescription.name}}</h1>
              <h2>{{seriesDescription.original_name}}</h2>
              <h3><lang-flag :iso="seriesDescription.original_language"/></h3>
              <font-awesome-icon v-for="i in starsAverageCalc(seriesDescription.vote_average)" :key="i" icon="fa-solid fa-star" />
              <font-awesome-icon v-for="i in getEmptyStars(seriesDescription.vote_average)" :key="i" icon="fa-regular fa-star"/>
              <h5>{{seriesDescription.overview}}</h5>
            </div>  
        </li>
    </ul>
   </div>



</template>

<script>

export default {
  name: 'MySeries',
  
  props: {
    seriesDescription: Object
  },
  methods: {
        starsAverageCalc (vote){
          let calc =  parseInt(Math.round(vote / 2));
          console.log(calc)
            return   calc;
        },
        getEmptyStars(vote) {
            let empty = parseInt(Math.round(5-(vote/2)));
            return empty;
        }
    }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.container {
  display: inline-block;
}

li {
  display: inline-block;
  position: relative;
  
}
.fa-star{
    color: yellow;
}

.poster {
  position: relative;
  z-index: 2;
}
.poster:hover {
  z-index: 0;
}
.descrizioneFilm:hover {
  z-index: 3;
}
.descrizioneFilm {
  position: absolute;
  top: 0;
  z-index: 1;
  background-color: black;
  color: white;
  width: 100%;
  height: 100%;
}

</style>