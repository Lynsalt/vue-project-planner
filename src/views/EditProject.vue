<template>
  <div class="container">
    <div id="main">
        <form @submit.prevent="updateProject">
        <label>Title:</label>
        <input type="text" required v-model="title">
        <label>Details:</label>
        <textarea required  v-model="details"></textarea>
        <button>Update Project</button>
        </form>
    </div>
  </div>
  <Footer/>
</template>

<script>
import Footer from '../components/Footer.vue'
export default {
    props:['id'],
    name:' EditProject',
    components:{
       Footer
    },
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
  },
  methods:{
      updateProject(){
        fetch(this.uri,{
            method: 'PATCH',
            headers: {'Content-Type': 'application/json'},
            body:JSON.stringify({ title : this.title, details: this.details})
        }).then(()=>{
            this.$router.push('/');
        }).catch(err=> console.log(err.message))
        
      }
  }
}
</script>

<style scoped>
.container{
  min-height:100%;
}
.filterNav{
   text-align:center;
}
</style>