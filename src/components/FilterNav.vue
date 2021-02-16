<template>
        <nav class="filter-nav">
            <button 
            @click="updateFilter('all')"
            :class="{active: current === 'all' }"
            >View All</button>
            <button 
            @click="updateFilter('completed')"
            :class="{active: current === 'completed'}"
            >Completed</button>
            <button 
            @click="updateFilter('inprogress')"
            :class="{active : current === 'inprogress'}"
            >In Progress</button>
        </nav>
</template>

<script>
export default {
    props:['current'],
    name: 'FilterNav',
  data(){
      return{

      }
  },
  methods:{
      updateFilter(by){
        this.$emit('filterChange', by) 
      }
  }
}
</script>

<style>
.container{
  min-height:100%;
}
   .filter-nav button{
       background: none;
       border: none;
       color:#bbb;
       outline:none;
       font-size:12px;
       text-transform:uppercase;
       margin-right:10px;
       letter-spacing:1px;
       font-weight:bold;
       cursor:pointer;
   }
   .filter-nav button.active{
       color:#555;
   }
</style>