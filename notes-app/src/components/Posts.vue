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
 
<style> 
</style>