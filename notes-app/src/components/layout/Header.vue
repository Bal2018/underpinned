<template>
 <!-- <v-card
    color="grey lighten-4"
    flat
    height="10px"
    tile
  > -->
  <div>
    <v-app-bar elevate-on-scroll dense    >  
        <!-- <v-app-bar-nav-icon></v-app-bar-nav-icon> -->
        <!-- <v-toolbar-title class="header">  -->
         
        <a href="/" >          
            <img src='../../../src/assets/UPLogo2.png' alt="UnderPinned Logo"  class="h-38" style="width: 300px" >
        </a>
        <v-spacer></v-spacer>
        <div id="nav">
        <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link>
        </div>
        
       <!-- </v-toolbar-title> -->
        <!--   <v-spacer></v-spacer>
            <v-toolbar-items class="center">Current Posts </v-toolbar-items>-->
    </v-app-bar>
    <v-sheet
      id="scrolling-techniques-7"
      class="overflow-y-auto"
      max-height="60"
    >
      <v-container style="height: 1500px;">
      </v-container>
    </v-sheet>
  </div>
</template>

<script> 
    export default {
        name: "Header" 
    }
</script>

<style scoped>
    .header { 
        background:  white;
        text-align: left;
        padding: 10px;
    }
    .header a {
        color: white;
        padding-right: 5px;
    }
</style>