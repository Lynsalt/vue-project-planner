<template>
  <footer class="container-fluid">
      <div class="container copyright"><span>{{ new Date().getFullYear() }}</span></div>
  </footer>
</template>

<script>
name: 'Footer'
</script>

<style scoped>
  
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