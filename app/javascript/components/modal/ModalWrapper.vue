<template>
  <div class="modal-wrapper flex-h-center" :class="{ 'modal-wrapper--active' : isActive }" @click.self="closeModal">
  </div>
</template>

<script>
  import { eventHub } from '../../vue.js'

  export default {
    name: 'modal-wrapper',

    computed: {
      isActive () {
        return this.$store.state.modal.isActive
      }
    },

    methods: {
      closeModal () {
        this.$store.commit('modal/updateModalStatus')
      },
    }
  }
</script>

<style lang="scss">
  .modal-wrapper {
    background-color: rgba(black, .6);
    
    display: none;
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: 5;

    &--active { display: flex; }
  }
</style>
