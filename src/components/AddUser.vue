<template>
  <div>
      <h1>User Add Form</h1>
      <form @submit="storeUser">
        <input type="text" v-model="name" placeholder="Enter Name .." required /><br><br>
        <input type="email" v-model="email" placeholder="Enter Email .." required /><br><br>
        <!-- <input type="submit" value="Add User" />   -->
        <button type="submit">Add User</button>
      </form>
  </div>
</template>

<script>
export default {
    name: "AddUser",
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
    button{
        min-height: 40px;
        /* width: 40px; */
        border-radius: 5%;
        border-color: transparent;
        background-color: #30336b;
        color: #fff;
        font-size: 20px;
        border: none;
        outline: none;
        padding: 0 15px;
        margin-top: 30px;
        box-shadow: 5px 5px 15px -5px rgba(0, 0, 0, 0.3);
    }
</style>