<template>
   <div class="container">
    <ul>
        <li>
            <h1>{{filmDescription.title}}</h1>
            <h2>{{filmDescription.original_title}}</h2>
            <h3><lang-flag :iso="filmDescription.original_language"/></h3>
            <h4>{{filmDescription.vote_average}}</h4>
            
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
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

li {
  display: inline-block;
  margin: 15px;
}

</style>