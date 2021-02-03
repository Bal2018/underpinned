<template>
  <div>
    <div v-bind:key="post.id" v-for="post in posts">
      <PostItem v-bind:post="post" v-on:del-post="$emit('del-post', post.id)"/>
    </div>
  </div>
</template>

<script>
import PostItem from "./PostItem";
export default {
  name: "Posts",
  components: {
    PostItem
  },
  props: ["posts"] 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h3 {
    margin: 40px 0 0;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: inline-block;
    margin: 0 10px;
  }
  a {
    color: #42b983;
  }
</style>