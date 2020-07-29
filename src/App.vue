<template>
  <div id="app">
    
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <transition v-on:enter="enter" v-on:leave="leave" v-bind:css="false" appear>
    <router-view></router-view>
    </transition>
    
    
  </div>
</template>

<script>
import {TimelineMax, /*TweenMax*/} from 'gsap';

export default {
  mounted(){
    let App = document.querySelector('#app');
    let tl = new TimelineMax();
    tl.fromTo(App, 1 , {y:2000},{y:0});
    tl.to(document.querySelector("#vuelogo"), 2 , {rotationY:180,repeat:-1});
  },
  methods:{
    enter(){
        let tl = new TimelineMax();
        tl.to(document.querySelector("#vuelogo"), 2 , {rotationY:180,repeat:-1});
    }
  }
}
</script>

<style>
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