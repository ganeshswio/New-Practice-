<template>
    <div id="register">
        <h3>Register</h3>
    <div class="">
        <form>
       
        <div class="">
             <label for="title"> Email:</label>
            <input type="text" id="email" v-model="email">
        </div>
        <div>
          <label for="content" >Password:</label>
            <input type="password" id="password" v-model="password">
        </div>
        <div class="">
                <button v-on:click="register">Register</button>
        </div>
         </form>
    
     </div>

    
    </div>
</template>

<script>
import * as firebase from 'firebase'
import db from './firebaseInit'
export default {
    name : 'register',
    data(){
        return{
            email:'',
            password:''
            
        }
    },


   methods:{
    //    register:function(e){
    //        firebase
    //        .auth()
    //        .createUserWithEmailandPassword(this.email,this.password)
    //        .then(
    //            user =>{
    //              alert ('account created for ${user.email}');
    //                this.$router.push('/');
    //        }),
    //        err =>{
    //            alert(err.message)
    //        }
    //     // console.log('register')
    //     e.preventDefault();
    register:function(e){
    firebase
    .auth()
    .createUserWithEmailAndPassword(this.email, this.password)
     .then(
              user =>{
                  console.log('worked')
                alert ('account created for ${user.email}');
    this.$router.push('/');
       })
    .catch(function(error) {
  // Handle Errors here.
  var errorCode = error.code;
  var errorMessage = error.message;
  // ...
});
    // }
   }
   }

}
</script>

<style>

</style>
