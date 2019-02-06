<template>
    <div id="dashboard">
     <h3>Dashboard</h3>
    
    <div>
        <router-link to="/new">
         ADD new
        </router-link>
   <button v-on:click="created">get</button>
        <li v-for="(emp ,index) in employees" :key="index">{{emp.name}}</li>
    </div>


    </div>
</template>

<script>
import db from './firebaseInit'
export default {
    name: 'dashboard',
    data(){
        return{
          employees:[]
        }
    },
    methods:{
            created(){
                db.collection("books").get().then((querySnapshot) => {
                    querySnapshot.forEach((doc) => {
                        console.log(doc)
                // console.log(`${doc.id} => ${doc.data()}`);
            });
            });
            }
    }
   

}
</script>

<style>
a{
    color:black;
}
</style>
