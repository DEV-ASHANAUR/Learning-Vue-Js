<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <!-- <h2>Hello Bangladesh</h2> -->
  <AddUser @add-user="storeUser" />
  <Show :allUser="users" />
</template>

<script>
import AddUser from './components/AddUser'
import Show from './components/Show'
import axios from 'axios'
export default {
  name: 'App',
  components: {
    AddUser,Show,
  },
  data() {
    return {
        users:[],
    };
  },
  methods:{
      storeUser:function (user){
        this.users = [user, ...this.users];
      }
  },
  async created(){
    try {
        const response = await axios.get("https://jsonplaceholder.typicode.com/users");
        console.log(response);
    } catch (error) {
      console.log(error);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
