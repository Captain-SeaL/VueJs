<template>
  <div class="vuex">
    <img alt="Vue logo" id="vuelogo" src="../assets/logo.png">
    <h1>This is an example of Vuex using.</h1>
    <h2>Count of posts is {{ postsCount }} </h2>
    <PostForm/>
    <hr>
    <transition-group appear v-on:enter="enter" v-bind:css="false">
    <div class="post" v-for="post in allPosts" :key="post.id">
        <h2>{{ post.title }}</h2>
        <p>{{ post.body }}</p>
        
    </div>
    </transition-group>
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
import PostForm from '../components/PostForm'
import {TimelineMax} from 'gsap'
//import * as gsap from 'gsap'
export default {
  name: "vuex",
  computed: mapGetters(['allPosts', 'postsCount']),
  
  methods: {
  ...mapActions(['fetchPosts']),
  enter(el,done){
        console.log("12");
        let tl = new TimelineMax();
        tl.fromTo(el,2,{x:-2000},{x:0},{complete: done});
        
        
    }
  },
  components: { PostForm },
  async mounted() {
    //this.$store.dispatch('fetchPosts')
    this.fetchPosts();
  }
}
</script>
<style scoped>

.post{
  border: 1px solid #ccc;
  border-radius: 5px;
  border-bottom: 1rem;
}
</style>