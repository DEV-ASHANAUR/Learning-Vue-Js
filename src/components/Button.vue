<template>
  <button type="submit">
      <slot></slot>
  </button>
</template>

<script>
export default {
    name:"Button",
}
</script>

<style>
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