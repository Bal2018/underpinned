<template>
  <div class="post-item  text-center"  >
    <input type="checkbox justify-center  " v-on:change="editPost">
    <span class="text-decoration-underline font-weight-medium justify-center d-flex "> {{post.title}} </span>
    <p class="font-weight-regular text-start">{{post.body}} </p>
    <v-spacer></v-spacer>
    <v-btn rounded color="red justify-center" dark @click="$emit('del-post', post.id)" v-ripple="{class:'green'} ">  <v-icon small > mdi-delete </v-icon>deletePost </v-btn> 
    <v-btn rounded color="green" dark @click="$emit('edit-post', post.id)" v-ripple="{class:'red'} "><v-icon small > mdi-pencil </v-icon>editPost </v-btn>    
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
  /* .del {
    background: red;
    color: white;
    border: none;
    padding: 5px 9px;
    cursor: pointer;
    float: right;
  } */
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
