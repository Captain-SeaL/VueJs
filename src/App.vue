<template>
  <div id="app">
    
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/Vuex">Vuex</router-link> |
      <router-link to="/Anime">Anime</router-link>
    </div>
    <transition name="fade" mode="out-in">
    <router-view></router-view>
    </transition>
    
    
  </div>
</template>

<script>


export default {
  
}
</script>

<style>
.fade-enter-active, .fade-leave-active {
  transform: translateX(-2000px);
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
  transform: translateX(0px);
  
}
.fade-enter, .fade-leave-active {
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
  
  transform: translateX(2000px);
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
  background: #cbfde6;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}


</style>