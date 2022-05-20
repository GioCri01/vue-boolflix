<template>

          <div class="box">
              <img :src="`https://image.tmdb.org/t/p/w500/${movieItem.poster_path}`" :alt="movieItem.title">
              <p>{{movieItem.title}}</p>
              <p>{{movieItem.original_title}}</p>
              <p>{{movieItem.original_language}}</p>
              <p>{{movieItem.vote_average}}</p>
          </div>
          

     
  
</template>

<script>
export default {
    name: "CardMovieComp",
    props:{
        movieItem : Object,
    }

}
</script >
 
<style leng="scss" scoped>
 .box{
        width: calc(100%/ 3 - 30px);
        padding: 15px;
        margin: 15px;
        background-color: rgba(0, 0, 0, 0.274);
        border-radius:10px ;
        
       
    }
    img{
        width: 100%;
    }

</style>