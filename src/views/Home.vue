<template>
 
  <div class="container">
   <div v-if="projects.length">
      <div v-for="project in projects" :key="project.id">
        <Singleproject :project="project" @delete="handleDelete" @complete="handleComplete"/>
      </div>
   </div>
  </div>
</template>

<script>
// @ is an alias to /src

import Singleproject from '../components/Singleproject'
export default {
  name: 'Home',
  components: {Singleproject},
  data(){
    return{
      projects: []
    }
  },
  mounted(){
    fetch(' http://localhost:3000/projects')
    .then(res => res.json())
    .then(data => this.projects = data)
    .catch(err => console.log(err.message))
  },
  methods:{
    handleDelete(id){
       this.projects = this.projects.filter(project =>{
         return project.id !== id
       })
    },
    handleComplete(id){
      let pro = this.projects.find(project =>{
        return project.id === id
      })
      pro.complete = !pro.complete
    }
  }

}
</script>
<style scoped>

</style>
