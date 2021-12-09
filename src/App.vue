<template>
  <SearchBox  @search="filtreUser"/>
  <User :listUsers="filtered" />
</template>

<script>
import SearchBox from '@/components/searchBox/SearchBox.vue'
import User from '@/components/user/User.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    User,
    SearchBox
  },
  data() {
    return {
      filtered:'',
      listUsers:''
    }
  },
  created() {
      axios.get("https://jsonplaceholder.typicode.com/users").then(result =>{
        this.listUsers = result.data;
        this.filtered = this.listUsers;
    })
  },
  methods: {
    filtreUser(value){
      if (value && value.length > 0) {
        this.filtered = this.listUsers.filter(user => (user.username).includes(value));
      }else{
        this.filtered = this.listUsers;
      }
    },
    
  },
}
</script>
<style>
#app {
  background: rgb(255, 250, 250);
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin: auto;
  width: 30%;
}
</style>
