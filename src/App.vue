<template>
   <div class="container-fluid">
    <div class="container">
      <Navbar/>
    </div>
  </div>
  <router-view/>
</template>

<script>
import Navbar from './components/Navbar.vue'
export default {
  components:{
    Navbar
  },
  data(){
    return{

    }
  }
}
</script>
<style>
body{
  background:#f2f2f2;
  margin:0;
  padding:0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
   max-width:100%;
   margin: 0 auto;
  color: #555;
}

.container{
  max-width:600px;
  margin:0px auto;
}
.container-fluid{
   width: 100%;
   height: 50px;
   padding: 1em 0;
   margin-bottom:20px;
   box-sizing:border-box;
   background:#333;
}
</style>
