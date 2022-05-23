<template>
  <main >
      <div class="container-fluid d-flex flex-wrap py-5 ">
          <CardMovieComp
      v-for="(movie,index) in movieList"
      :key="`movie-${index}`"
      :movieItem="movie"
      :filterApi="FilterValue"
      
      />
      </div>
      
  </main>
</template>

<script>

import CardMovieComp from "./CardMovieComp.vue"

export default {
    name: "MainComp",
    components:{
        CardMovieComp,
    },

    props:{
        movieList : Array,
        FilterValue :String,
        
    }

}
</script>

<style lang="scss" scoped>
main{
    
    
    background-color: rgba(0, 0, 0, 0.904);
    

   
}

</style>