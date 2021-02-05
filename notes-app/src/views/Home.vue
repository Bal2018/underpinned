<template> 
  <div class="home">
    <h1 class="py-6 display-2 text-center justify-center"> Current Posts </h1>
    <AddPost v-on:add-post="addPost"/>
    <Posts v-bind:posts="posts"  v-on:del-post="deletePost"/>
  </div> 
</template>

<script> 
import Posts from "../components/Posts";
import AddPost from '../components/AddPost';
import axios from 'axios';

export default {
  name: 'Home',
  components: { 
    Posts,
    AddPost
  },
  data(){
    return {
      posts: []
    }
  },
  methods: {
    deletePost(id){
      axios.delete(`https://jsonplaceholder.typicode.com/posts/${id}`)
      .then(() => this.posts = this.posts.filter(post =>post.id !== id))
     .catch(err => console.log(err));
    },
    addPost(newPost) {
      const {title, body} = newPost;
      axios.post('https://jsonplaceholder.typicode.com/posts ', {title,body})
      .then(res => this.posts = [...this.posts, res.data])
     .catch(err => console.log(err));
    } 
  },
  created(){
    axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10')
    .then(res => this.posts = res.data)
    .catch(err => console.log(err));
  }
}
</script>

<style>
  /* *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    }
  *body{
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
  .submitButton {
    display: inline-block;
    border: none;
    background: orange;
    color: white;
    padding: 7px 20px;
    cursor:pointer;
  }
  submitButton:hover {
    background: rebeccapurple;
  } */
</style>