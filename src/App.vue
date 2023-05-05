<template>
  <h1 ref="name">Vue</h1>
  <button @click="changeName">click</button>
  <Modal :header="header" del="Are you sure want to delete?" :content="content" :theme="theme"/>
</template>

<script>
// Modal => any name
import Modal from "./components/App-Modal.vue"
  export default {
    data(){
      return {
        name : "MinKhant",
        header : "Login success",
        content : "Welcome Min Khant",
        theme : "success",
      }
    },
    methods :{
      changeName(){
        this.$refs.name.textContent = this.name;
      }
    },
    components:{
      Modal
    }
  }
</script>

<!-- scoped mean css effect are only effect in curret file -->
<style scoped>
  h1{
    color: aqua;
  }
</style>