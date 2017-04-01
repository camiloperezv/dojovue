<template lang="html">
  <div>
      <h2>Users View</h2>
      <ul>
        <li v-for="user in users">
          {{ user.name }}
        </li>
      </ul>
  </div>
</template>

<script type="text/javascript">
  import axios from 'axios';
  export default{
    data(){
      return{
        users:[]
      }
    },
    mounted(){
      axios.get('https://jsonplaceholder.typicode.com/users')
        .then(success=>{
          this.users = success.data;
        },error=>{
          console.log('oppppps',error);
        });
    }
  }
</script>
<style type="text/css">
  
</style>