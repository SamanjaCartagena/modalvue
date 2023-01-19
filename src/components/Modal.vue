<template>
<transition name="modal-fade">
  <div class="modal-backdrop">
    <div class="modal" role="dialog"
    aria-labelledby="modalTitle"
    aria-describedby="modalDescription">
      <header class="modal-header" id="modalTitle">
        <slot name="header">
          This is the default title!
        </slot>
        <button
          type="button"
          class="btn-close"
          @click="close"
          aria-label="CloseModal"
        >
          x
        </button>
      </header>

      <section class="modal-body" id="modalDescription">
        <slot name="body">
          This is the default body!
        </slot>
       </section>

      <footer class="modal-footer" id="modalFooter">
        <slot name="footer">
          This is the default footer!
        </slot>
        <button
          type="button"
          class="btn-green"
          @click="close"
        >
          Close Modal
        </button>
      </footer>
    </div>
  </div>
</transition>
</template>

<script>
export default {
    methods:{
        close(){
            this.$emit('close')
        }
    }

}
</script>

<style>
.modal{
    background:#FFFFFF;
    box-shadow:2px 2px 20px 1px;
    overflow-x:auto;
    width:300px;
    height:300px;
    display:flex;
    flex-direction:column;
    z-index:5000;
}
.modal-header,
.modal-footer
{
  padding:15px;display:flex;
}
.modal-header{
    position: relative;
    border-bottom:1px solid #eeeeee;
    color:#4AAE9B;
    background: white;
    justify-content: space-between;

}
.modal-footer{
    border-top:1px solid #eeeeee;
    flex-direction: column;
    justify-content: flex-end;
    color:#4AAE9B;


}
.modal-body{
    position: relative;
    padding:20px 10px;
        color:#4AAE9B;
            background: white;


}
.btn-close{
    position: relative;
    top:0;
    right:0;
    color:#4AAE9B;
    border:none;
    font-size: 20px;
    padding:10px;
    cursor:pointer;
    font-weight:bold;
    background: white;
}
.btn-green{
    color:white;
    background:#4AAE9B;
    border:1px solid #4AAE9B;
    border-radius: 2px;
}
.modal-fade-enter,
.modal-fade-leave-to{
    opacity: 0;
}
.modal-fade-enter-active,
.modal-fade-leave-active{
    transition: opacity .5s ease;
}
</style>