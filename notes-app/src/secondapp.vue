<template>
<v-app>
  <div id="app">
    <Header />
   
    <AddPost v-on:add-post="AddPost"/>
     <v-content>
    <posts v-bind:posts="posts" v-on:del-post="deletePost"/>
     </v-content>
  </div>
  </v-app>
</template>

<script> 
import Posts from "./components/Posts";
import Header from "./components/layout/Header";
import AddPost from './components/AddPost';
import axios from 'axios';
export default {
  name: 'App',
  components: { 
    Posts,
    Header,
    AddPost
  },
  data(){
    return {
      posts: [

      ]
    }
  },
  methods: {
    deletePost(id){
      axios.delete(`https://jsonplaceholder.typicode.com/posts/${id}`)
      .then(() => this.posts = this.posts.filter(post =>post.id !== id))
     .catch(err => console.log(err));
    },
    AddPost(newPost) {
      const {title, body} = newPost;
      axios.post('https://jsonplaceholder.typicode.com/posts ', {title,body})
      .then(res => this.posts = [...this.posts, res.data])
     .catch(err => console.log(err));
    } 
  },
  created(){
    axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10')
    // .then(res => res.json())
    .then(res => this.posts = res.data)
    .catch(err => console.log(err));
  }
}
</script>

<style>
  *{
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
  }
</style>