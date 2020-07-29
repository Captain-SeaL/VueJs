<template>
  <div class="vuex">
    <img alt="Vue logo" id="vuelogo" src="../assets/logo.png">
    <h1>This is an example of Vuex using.</h1>
    <h2>Count of posts is {{ postsCount }} </h2>
    <PostForm/>
    <hr>
    <div class="post" v-for="post in allPosts" :key="post.id" >
        <h2>{{ post.title }}</h2>
        <p>{{ post.body }}</p>
    </div>
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
import PostForm from '../components/PostForm'
export default {
  name: "vuex",
  computed: mapGetters(['allPosts', 'postsCount']),
  
  methods: mapActions(['fetchPosts']),
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