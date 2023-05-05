<template>
  <h1 ref="name">Vue</h1>
  <button @click="changeName">click</button>

  <div v-if="show_modal">
    <Modal :theme="theme" @close ="show_modal = false">
      <!-- user slot -->
      <h1>Login Success</h1>
      <p> Welcome Min Khant</p>
      <!--  -->
      <!-- slot with name -->
      <template v-slot:links>
        <a href="">Sign up</a>
        <a href="">Register</a>
      </template>
    </Modal>
  </div>
  <!-- event modifyer click.right => only work when right click -->
  <button @click="show_modal = true">Show Modal</button>


  <div v-if="del_active">
    <Modal @close="del_active = false" theme="danger">
      <h1>Are you sure want to delete</h1>
      <p>Cannot restore it again</p>
    </Modal>
  </div>
  <button @click="del_active = true">Delete</button>

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
        show_modal : false,
        del_active : false,
      }
    },
    methods :{
      changeName(){
        this.$refs.name.textContent = this.name;
      },
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