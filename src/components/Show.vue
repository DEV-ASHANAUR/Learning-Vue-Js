<template>
  <div>
      <h4 v-for="(user,index) in allUser" :key="index">
          {{ user.name }} - {{ user.email }}
      </h4>
  </div>
</template>

<script>
export default {
    name:"Show",
    props:["allUser"],
}
</script>

<style>

</style>