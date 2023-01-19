<template>
 
    <button type="button" class="btn" @click="showModal">Open Modal!</button>
<Modal
  v-show="isModalVisible"
  @close="closeModal"
>
  <template v-slot:header>
    This is a new modal header.
  </template>

  <template v-slot:body>
    This is a new modal body.
  </template>

  <template v-slot:footer>
    This is a new modal footer.
  </template>
</Modal>  
  
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  components:{Modal},
  data(){
    return {
      isModalVisible:false
    }
  },
  methods:{
    showModal(){
      this.isModalVisible=true
    },
    closeModal(){
      this.isModalVisible=false;
    }
  }

}
</script>

<style>
.btn{
  z-index:0;
  position: absolute;
  left:50%;
  top:40%;

}
</style>
