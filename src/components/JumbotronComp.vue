<template>
  <div class=" jumbotron">
      <img :src="`https://image.tmdb.org/t/p/w500/${posterImg.poster_path}`" alt="">
  </div>
</template>

<script>
export default {
    name: "JumbotronComp.vue",

    
}
</script>

<style lang="scss" scoped>
.jumbotron{
    height: 500px;
    
    img{
        width: 100%;
        height: 100%;
        object-fit:cover;
    }
}

</style>