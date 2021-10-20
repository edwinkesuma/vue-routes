<template>
  <div v-if="job">
    <h1>This is a jobs details page</h1>
    <p>{{job.name}}</p>
    <p>The id of this page is {{id}}</p>
    <p>{{job.details}}</p>
  </div>
  <div v-else>
    <p>Loading job detail</p>
  </div>
  
</template>

<script>
export default {
    props:['id'],
    data(){
      return{
        job : null,
      }
    },
    mounted(){
      fetch('http://localhost:3000/jobs/'+ this.id)
        .then(res => res.json())
        .then(data => this.job = data)
        .catch(err => console.log(err.message))
    }
}
</script>

<style>

</style>