<template>
    <nav class="main-nav">
        <router-link :to="{name: 'Home'}">Projects</router-link>
        <router-link :to="{name: 'AddProject'}">Add a new Project</router-link>
    </nav>
</template>
<script>
export default {
    name: 'Navbar',
    data(){
        return{
            
        }
    }
}
</script>
<style>
.main-nav a{
    display:inline-block;
    text-decoration: none;
    margin: 0 1em 0 0;
    color:#fff;
    font-size: 1.125rem;
}
a.router-link-active{
    border-bottom:2px solid #00ce89;
}
</style>