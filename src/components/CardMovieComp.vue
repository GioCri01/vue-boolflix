<template>
        
            <div v-if="filterApi === ''|| filterApi ==='movie'" class="box position-relative">
                <img v-show="movieItem.poster_path === null" src="https://www.ibs.it/images/9788872265703_0_0_350_75.jpg" :alt="movieItem.title">
              <img :src="`https://image.tmdb.org/t/p/w500/${movieItem.poster_path}`" :alt="movieItem.title">
              <div class="box-info">
                  
                <h2>{{movieItem.title}}</h2>
                <p>{{movieItem.original_title}}</p>
                <p>{{movieItem.release_date}}</p>
                <div class="overview"><p >{{movieItem.overview}}</p></div>
                
                <p><lang-flag :iso="movieItem.original_language" /></p>
                <p>{{movieItem.original_language}}</p>
                <p  > 
                <star-rating
                :rating="movieItem.vote_average/2"
                :max-rating="5"
                :star-size="20"
                :read-only="true"
                :round-start-rating="false"
                
                ></star-rating></p>
              </div>
              
            </div>
            <div v-else class="box position-relative">
              <img :src="`https://image.tmdb.org/t/p/w500/${movieItem.poster_path}`" :alt="movieItem.title">
              <div class="box-info">
                <h2>{{movieItem.name}}</h2>
                <p>{{movieItem.original_name}}</p>
                <p>{{movieItem.first_air_date}}</p>
                <div class="overview"><p >{{movieItem.overview}}</p></div>
                <p><lang-flag :iso="movieItem.original_language" /></p>
                <p>{{movieItem.original_language}}</p>
                <p >
                <star-rating
                :rating="movieItem.vote_average/2"
                :max-rating="5"
                :star-size="20"
                :read-only="true"
                :round-start-rating="false"
                
                ></star-rating> 
                
                
                </p> 
            
                
                
              </div>
              
            </div>
       

            
          

     
  
</template>


<script>
import LangFlag from 'vue-lang-code-flags';
import StarRating from 'vue-star-rating'

export default {
    name: "CardMovieComp",
    
    props:{
        movieItem : Object,
        filterApi : String
    },
    components:{
        LangFlag,
        StarRating,
        
    }

}
</script >
 
<style lang="scss" scoped>
 .box{
        width: calc(100%/ 5 - 30px);
        
        
        margin: 15px;
        background-color: rgba(0, 0, 0, 0.274);
        text-align: center;
        transition: all 0.3s;

        img{
        width: 100%;
        height: 100%;
        
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
        cursor: pointer;
        padding: 10px;
        background-color: rgba(0, 0, 0, 0.774);
        display: none;
        
        transition: all 0.3s;
        
        .overview{
            
            width: 100%;
            height: 200px;
            margin-bottom:10px ;
            overflow: hidden;
            overflow-y: auto;
        }
        
    }
    

</style>