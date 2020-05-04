<template>
  <div>
    <div id="nav">
            <router-link to="/">API DE BLAGUES</router-link><br></br>
    </div>
    <router-view/>
  </div>
</template>

<style>
* {
  margin: 0%;
  padding: 0%;
  
}



#nav a.router-link-exact-active {
  color:  #000000;
  position: absolute;
  top: 5px;
  left: 40PX;
  text-decoration: none;
}
</style>
