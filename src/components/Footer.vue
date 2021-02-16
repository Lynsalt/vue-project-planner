<template>
  <footer class="container-fluid">
      <div class="container copyright"><span>{{ new Date().getFullYear() }}</span></div>
  </footer>
</template>

<script>
name: 'Footer'
export default {

}
</script>

<style>
   footer{    
       padding:1em 0;
       background-color:#444;
   }
   .copyright, a{
       text-align:center;
       color:antiquewhite;
   }
   a{
       text-decoration:none;
       color:#00ce89;
       font-size:.9rem;
   }
</style>