<template>
   <div class="container">
    <ul>
        <li>
            <h1>{{seriesDescription.name}}</h1>
            <h2>{{seriesDescription.original_name}}</h2>
            <h3><lang-flag :iso="seriesDescription.original_language"/></h3>
            <h4>{{seriesDescription.vote_average}}</h4>
        </li>
    </ul>
   </div>



</template>

<script>

export default {
  name: 'MySeries',
  
  props: {
    seriesDescription: Object
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