<template>
  <div id="app">
     <nav class="navbar navbar-expand-sm navbar-dark sticky-top d-inline-flex justify-content-between w-100" style="background-color: rgb(14, 39, 78);">
  <div class="navbar" style="position: absolute; left: 50%; top:0%; transform: translateX(-50%); ">
     <router-link to="/" class="text-decoration-none"> MOVIE BOX</router-link>
  </div>
  <div>
    <div class="d-block d-sm-none" style="height:40px;" >
      <button style="position: absolute;left:10px; top: 10px;" class="navbar-toggler mr-auto border-0" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation"> 
        <span class="navbar-toggler-icon"></span>
      </button>  
    </div>
    <div class="collapse navbar-collapse py-0 w-50" id="navbarNav">
      <ul class="navbar-nav mr-auto w-50 pr-0">
          <li class="nav-item active">
            <router-link to="/" class="text-decoration-none mr-3">Movie</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/video" class="text-decoration-none">Video</router-link>
          </li>
      </ul>
  </div>  
  </div>
</nav> 
      
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.nav-item {
  font-weight: bold;
  color: #2c3e50;
}

</style>
