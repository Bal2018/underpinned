<template>
    <nav>
        <v-toolbar app dense>
          
            <v-toolbar-title>
                <span >
                    <a href="/"  >          
                        <img src='../../src/assets/UPLogo2.png' alt="UnderPinned Logo"  class="h-38  " style="width: 300px" >
                    </a>
                </span>
            </v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn flat color="pink"> 
                <router-link to="/"><span>Home</span></router-link>
            </v-btn>
            <v-btn flat color="red">
                <router-link to="/about"><span>About</span></router-link>
            </v-btn>
        </v-toolbar>
        
    </nav> 
</template>

<script>
export default {
    data() {
        return {
            drawer :false
            
        }
    }
}
</script>
<style>

</style>