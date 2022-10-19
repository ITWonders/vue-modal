<template lang="pug">
transition(name='iw-modal')
  .iw-modal-template
    .iw-modal-wrapper
      .iw-modal-container
        .modal-header
          slot(name='header')
            | default header
        .modal-body
          slot(name='body')
            | default body
        .modal-footer
          slot(name='footer')
            | default footer
            button.modal-default-button(@click="$emit('close')")
              | OK
</template>

<script>
    export default {
        mounted() {
        }
    }
</script>

<style lang="scss">
.iw-modal-template{
  position: fixed;
  z-index: 10001;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, .5);
  display: table;
  transition: opacity .3s ease;

  .iw-modal-wrapper {
    vertical-align: middle;
    overflow: auto;
    height: 100vh;
    position: relative;
  }

  .iw-modal-wrapper .iw-modal-container {
    //   width: 50%;
    //   min-width: 500px;
      margin: 0px auto;
      padding: 20px 30px;
      background-color: #fff;
      border-radius: 2px;
      box-shadow: 0 2px 8px rgba(0, 0, 0, .33);
      transition: all .3s ease;
      font-family: Helvetica, Arial, sans-serif;
      .modal-body {
        margin: 20px 0;
      }
    }
  }


/*
 * The following styles are auto-applied to elements with
 * transition="modal" when their visibility is toggled
 * by Vue.js.
 *
 * You can easily play with the modal transition by editing
 * these styles.
 */

.iw-modal-enter {
  opacity: 0;
}

.iw-modal-leave-active {
  opacity: 0;
}

.iw-modal-enter .iw-modal-container,
.iw-modal-leave-active .iw-modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}

/* mobile/base */
/* mobile landscape */
@media all and (min-width: 480px) {
}
/* tablet */
@media all and (min-width: 768px) {
}
/* desktop */
@media all and (min-width: 1024px) {
    .iw-modal-template{
        .iw-modal-wrapper .iw-modal-container {
            width: 50%;
            min-width: 500px;
        }
    }
}
/* desktop wide */
@media all and (min-width: 1200px) {
}
</style>
