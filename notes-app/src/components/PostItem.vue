<template>
  <div class="post-item" >
     <p>
       <input type="checkbox" v-on:change="editPost">
       {{post.title}} 
       {{post.body}}
       <button @click="$emit('del-post', post.id)" class="del"></button>
      </p>
  </div>
</template>

<script>
  export default {
    name: 'PostItem',
    props: ["post"],
    methods: {
      editPost ( ){     //Need to add functionality here 
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .post-item {
    background:white;
    padding: 20px;
    border-bottom: 1px wheat dotted;
  }
  .del {
    background: red;
    color: white;
    border: none;
    padding: 5px 9px;
    cursor: pointer;
    float: right;
  }
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
    color: white;
  }
</style>
