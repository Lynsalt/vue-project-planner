<template>
 
  <div class="container">
    <FilterNav @filterChange="current = $event" :current="current"/>
   <div v-if="projects.length">
      <div v-for="project in filteredProjects" :key="project.id">
        <Singleproject :project="project" @delete="handleDelete" @complete="handleComplete"/>
      </div>
   </div>
  </div>
</template>
ddf
<script>
// @ is an alias to /src
import Singleproject from '../components/Singleproject'
import FilterNav from '../components/FilterNav'
export default {
  name: 'Home',
  components: {Singleproject,FilterNav},
  data(){
    return{
      projects: [],
      current: 'all'
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
  },
  computed:{
      filteredProjects(){
          if(this.current === 'completed'){
            return this.projects.filter(project => project.complete)
          }

          if(this.current === 'inprogress'){
            return this.projects.filter(project => !project.complete)
          }
          return this.projects
      }
  }

}
</script>
<style scoped>

</style>
