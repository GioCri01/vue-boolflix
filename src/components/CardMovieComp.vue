<template>

          <div v-if="filterApi === 'movie'" class="box position-relative">
              <img :src="`https://image.tmdb.org/t/p/w500/${movieItem.poster_path}`" :alt="movieItem.title">
              <div class="box-info">
                <h2>{{movieItem.title}}</h2>
                <p>{{movieItem.original_title}}</p>
                <p>{{movieItem.release_date}}</p>
                <p >{{movieItem.overview}}</p>
                <p><lang-flag :iso="movieItem.original_language" /></p>
                <p>{{movieItem.original_language}}</p>
                <p>Valutazione : {{movieItem.vote_average}} su 10</p>
              </div>
              
            </div>
            <div v-else class="box position-relative">
              <img :src="`https://image.tmdb.org/t/p/w500/${movieItem.poster_path}`" :alt="movieItem.title">
              <div class="box-info">
                <h2>{{movieItem.name}}</h2>
                <p>{{movieItem.original_name}}</p>
                <p>{{movieItem.first_air_date}}</p>
                <p >{{movieItem.overview}}</p>
                <p><lang-flag :iso="movieItem.original_language" /></p>
                <p>{{movieItem.original_language}}</p>
                <p>Valutazione : {{movieItem.vote_average}} su 10</p>
              </div>
              
            </div>

            
          

     
  
</template>


<script>
import LangFlag from 'vue-lang-code-flags';
export default {
    name: "CardMovieComp",
    
    props:{
        movieItem : Object,
        filterApi : String
    },
    components:{
        LangFlag,
    }

}
</script >
 
<style lang="scss" scoped>
 .box{
        width: calc(100%/ 4 - 30px);
        
        padding: 15px;
        margin: 15px;
        background-color: rgba(0, 0, 0, 0.274);
        border-radius:10px ;
        transition: all 0.3s;

        img{
        width: 100%;
        }
        &:hover{
            transform: scale(1.08);
        }


        &:hover .box-info{
            display: block;
        }
        
       
       
    }
    .box-info{
        color: white;
        text-align: center;
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        border-radius: 10px;
        padding: 10px;
        background-color: rgba(0, 0, 0, 0.774);
        display: none;
        overflow: hidden;
        overflow-y:scroll ;
        transition: all 0.3s;
        
        
        
    }
    

</style>