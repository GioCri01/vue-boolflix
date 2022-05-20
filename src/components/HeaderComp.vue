<template>
  <header>
      <div class="container-fluid d-flex justify-content-between align-items-center">
          <img src="https://www.romait.it/wp-content/uploads/2022/04/Netflix-logo.jpg" alt="">
          <div class="d-flex ">
              <input type="text" placeholder="cerca film" class="form-control mx-2">
              <button class="btn bg-danger"> asd</button>
          </div>
      
  </div>
  </header>
</template>

<script>
export default {
    name: "HeaderComp",

}
</script>

<style lang="scss" scoped>
header{
    height: 100px;
    background-color: black;
    img{
        width: 175px;
    }
    
}


</style>