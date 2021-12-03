<template>
  <div class="modal" :class="{'show': showModal}">
      <div>
          <slot/>
      </div>
      <div>
          <button @click="hide">fermer</button>
      </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            showModal: false
        }
    },
    props: {
        title: {
            type: String,
            default: ''
        },
    },
    methods: {
        show() {
            this.showModal = true;
        },
        hide() {
            this.showModal = false;
        }
    }
}
</script>

<style>
.modal {
    position: fixed;
    top: 50%;
    left: 50%;
    display: none;
    padding: 1em;
    background-color: #888;
    border: 1px solid #222;
}
.modal.show {
    display: block;
}
</style>