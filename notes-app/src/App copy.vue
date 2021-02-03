<template>
  <!-- <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    > -->
    <div id="app" >
        <!-- <v-row class="text-center">
        <v-col cols="12">
          <v-img
            :src="require('./assets/upLogo.svg')"
            class="my-3"
            contain
            height="200"
          />
        </v-col>
        </v-row>     -->
        <Header />
        <!-- <AddNote v-on:add-note="AddNote"/>
        <Notes v-bind:notes="notes" v-on:del-note="deleteNote"/> -->
      </div>

      <!-- <v-spacer></v-spacer>
      
    </v-app-bar>

    <v-main>
       
    </v-main>
  </v-app> -->
</template>

<script>
  // import Notes from "./components/Notes";
  import Header from "./components/layout/Header";
  // import AddNotes from './components/AddNotes';
  import axios from 'axios';

  export default {
    name: 'App',

    components: {
      // Notes,
      Header
      // AddNotes
  },
  data(){
    return {
      notes: [
      ]
    }
  },
  // methods: {
  //   deleteNote(id){
  //     axios.delete(`https://jsonplaceholder.typicode.com/posts/${id}`)
  //     .then(() => this.notes = this.notes.filter(note =>note.id !== id))
  //    .catch(err => console.log(err));
  //   },
  //   AddNote(newNote) {
  //     const {title, body} = newNotes;
  //     axios.post('https://jsonplaceholder.typicode.com/posts ', {title,body})
  //     .then(res => this.notes = [...this.notes, res.data])
  //    .catch(err => console.log(err));
  //   }
  // },
  created(){
    axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10')
    // .then(res => res.json())
    .then(res => this.notes = res.data)
    .catch(err => console.log(err));
  }
}
</script>