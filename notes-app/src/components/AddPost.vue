<template>
    <div>
        <form @submit="addPost">
            <input type="text" v-model="title" name="title " placeholder="Post Title" >
            <input type="text" v-model="body" name="body" placeholder="Post Details" >
            <input type="submit" value="submit" class="submitButton" >
        </form>
    </div>
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
            // the above constructed the data we wanted, and now we need 
            // to send this to the parent class using emit
            if ((this.title) && (this.body)) {         //conditional emit if both field have been entered
                this.$emit('add-post', newPost);
            }
            this.title = '';            //blank title and body input fields
            this.body = '';
        }
    }
}
</script>

<style scoped>
    form { display: flex;}
    input[type="text"]{
        flex : 10;
        padding: 5px;
    }
    input[type="submit"]{
        flex : 2; 
    }
</style>