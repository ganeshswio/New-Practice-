<template>
    <div id="new-employee">
       <h3>New Employee</h3>
     <div class="">
            <label for="title">Blog title :</label>
            <input type="text" v-model="title"> <br> <br>
            <label for="content">Blog content :</label>
            <input type="text" v-model="content">
            <button v-on:click.prevent="post">POST BLOG</button>
     </div>

    </div>
</template>

<script>
import db from './firebaseInit'
export default {
    name : 'new-employee',
    data(){
        return{
            title:null,
            content:null
            
        }
    },
    methods:{
        post(){
              db.collection("books").add({
                title:this.title,
                content:this.content
                })
                .then(function(docRef) {
                console.log("Document written with ID: ", docRef.id);
                })
                .catch(function(error) {
                console.error("Error adding document: ", error);
                });  

        }
    }

}
</script>

<style>

</style>
