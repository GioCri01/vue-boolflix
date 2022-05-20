<template>
  <main >
      <div class="container d-flex flex-wrap ">
          <CardMovieComp
      v-for="(movie,index) in movieList"
      :key="`movie-${index}`"
      :movieItem="movie"
      
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
    }

}
</script>

<style lang="scss" scoped>
main{
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.514);

   
}

</style>