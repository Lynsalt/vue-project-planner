<template>
  <div class="container">
    <form>
      <label>Title:</label>
      <input type="text" required v-model="title">
      <label>Details:</label>
      <textarea required  v-model="details"></textarea>
      <button>Edit Project</button>
    </form>
  </div>
</template>

<script>
export default {
    props:['id'],
    name:' EditProject',
  data(){
      return{
         title: '',
         details: '',
         uri: 'http://localhost:3000/projects/' + this.id
      }
  },
  mounted(){
       fetch(this.uri)
       .then(res=> res.json())
       .then(data=>{
           this.title = data.title
           this.details = data.details
       })
  }
}
</script>

<style>

</style>