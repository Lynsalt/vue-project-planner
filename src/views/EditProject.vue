<template>
  <div class="container">
    <form @submit.prevent="handleSubmit">
      <label>Title:</label>
      <input type="text" required v-model="title">
      <label>Details:</label>
      <textarea required  v-model="details"></textarea>
      <button>Add Project</button>
    </form>
  </div>
</template>

<script>
export default {
  data(){
      return{

      }
  }
}
</script>

<style>

</style>