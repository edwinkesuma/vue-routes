<template>
  <div>
      <h1>This is a jobs page</h1>
      <div v-for="job in jobs" :key="job.id" class="job">
          <router-link :to="{name:'JobsDetail', params:{id: job.id}}">
              <h2>{{job.name}}</h2>
          </router-link>
      </div>
  </div>
</template>

<script>
export default {

    data(){
        return{
            jobs: [
                {name: 'Web Developer', id: 1},
                {name: 'Web Design', id: 2},
                {name: 'Mobile Developer', id: 3},
            ]
        }
    }

}
</script>

<style>
    .job h2{
        background: #f4f4f4;
        padding: 20px;
        border-radius: 10px;
        margin: 10px auto;
        max-width: 600px;
        cursor: pointer;
        color: #444;
    }
    .job h2:hover{
        background: #ddd;
    }
    .job a{
        text-decoration: none;
    }
</style>