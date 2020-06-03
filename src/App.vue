<template>
  <div id="app">
     <nav class="navbar navbar-expand-sm navbar-light sticky-top d-inline-flex justify-content-between w-100" style="background-color:white; box-shadow: 0 2px 2px -2px rgba(0,0,0,.2);">
  <div class="navbar" style="position: absolute; left: 50%; top:0%; transform: translateX(-50%); ">
     <router-link to="/" class="text-decoration-none nav-links"> MOVIE BOX</router-link>
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
            <router-link to="/" class="text-decoration-none nav-links mr-3">Movie</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/video" class="text-decoration-none nav-links">Video</router-link>
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
  color: #3fb883;
}

.nav-links{
  color: #3fb883;
  font-weight: bold;
}
</style>
