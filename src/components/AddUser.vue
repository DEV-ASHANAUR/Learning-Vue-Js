<template>
  <div>
      <h1>User Add Form</h1>
      <form @submit="storeUser">
        <input type="text" v-model="name" placeholder="Enter Name .." required /><br><br>
        <input type="email" v-model="email" placeholder="Enter Email .." required /><br><br>
        <Button>Add User</Button><br>
        <Button>Registation</Button>
      </form>
  </div>
</template>

<script>
import Button from './Button'
export default {
    name: "AddUser",
    
    components:{
        Button,
    },
    data() {
        return {
            name: "",
            email: "",
        };
    },
    methods:{
        storeUser:function (e){
            e.preventDefault();
            this.$emit("add-user",{name: this.name,email: this.email});
            this.name = "";
            this.email = "";
        }
    },
}
</script>

<style>
    input {
        text-align: center;
        height: 30px;
        top: 10px;
        /* border: none; */
        /* background: transparent; */
        font-size: 20px;
        font-weight: 500;
        width: 30%;
        /* border-bottom: 2px solid #8566aa; */
        /* outline: none; */
    }
    
</style>