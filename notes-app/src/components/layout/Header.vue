<template>
 <!-- <v-card
    color="grey lighten-4"
    flat
    height="10px"
    tile
  >
    <v-toolbar app dense>  
        <v-app-bar-nav-icon></v-app-bar-nav-icon>
        <v-toolbar-title class="header"> -->
    <header class="header">
    <img  src='../../../src/assets/UPLogo2.png' alt="UnderPinned Logo"  style="width: 200px">
    <span class="center">Current Posts </span>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    </header>
        <!-- </v-toolbar-title>
         <v-spacer></v-spacer>
            <v-toolbar-items class="center">Current Posts </v-toolbar-items>
    </v-toolbar>
 </v-card> -->
</template>

<script> 
    export default {
        name: "Header" 
    }
</script>

<style scoped>
    .header { 
        background:  white;
        text-align: center;
        padding: 10px;
    }
    .header a {
        color: white;
        padding-right: 5px;
    }
</style>