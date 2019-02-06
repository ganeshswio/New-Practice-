<template>
    <div id="navbar">
     <nav>
         <router-link to="/">Dashboard</router-link>
         <router-link to="/login">Login</router-link>
         <router-link to="/register">Register</router-link>


     </nav>
    </div>
</template>

<script>
export default {
    name : 'navbar',
    data(){
        return{
            
        }
    }

}
</script>

<style>
nav {
    background-color: green;
}
a{
    color:white;
    padding: 10px;
}
</style>
