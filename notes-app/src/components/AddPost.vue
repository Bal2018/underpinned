<template>
<v-container>
    <v-row justify="space-around">

    <div>
        <form @submit.prevent="addPost">
            <input type="text" v-model="title" name="title " placeholder="Post Title" >
            <input type="text" v-model="body" name="body" placeholder="Post Details" >
            <v-btn depressed color="orange" rounded large type="submit" value="Add Post"   class="submitButton"  >
                Add Post
            </v-btn>
        </form>
    </div>
    </v-row>
</v-container>
</template>
<script> 

export default {
    name: "AddPost",
    data(){
        return{ title:'',
        body: ''}
    },
    methods: {
        addPost(e){
            e.preventDefault();
            const newPost = { 
                title: this.title,
                body: this.body
            }
            
            if ((this.title) && (this.body)) {          
                this.$emit('add-post', newPost);
            }
            this.title = '';             
            this.body = '';
        }
    }
}
</script>

<style scoped>
    form { display: flex; border-block-style: double ;  }
    input[type="text"]{
        flex : 10;
        padding: 10px;
        margin: 10px;
    }
    input[type="submit"]{
        flex : 2; 
    }
</style>