<template>
   <div class="container">
    <ul>
        <li>
            <h1>{{filmDescription.title}}{{filmDescription.name}}</h1>
            <h2>{{filmDescription.original_title}}</h2>
            <h3>{{filmDescription.original_language}}</h3>
            <h4>{{filmDescription.vote_average}}</h4>
            
        </li>
    </ul>
   </div>



</template>

<script>
export default {
  name: 'MyCard',
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