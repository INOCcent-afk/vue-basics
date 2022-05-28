<template>
  <div role="dialog" class="modal">
    <slot>default content</slot>
    <button @click="closeModal">Close Modal</button>
    <div class="">
      <slot name="links"></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalVue",
  props: [],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.modal {
  width: 400px;
  border: 1px solid;
  height: 400px;
  position: fixed;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  background-color: #000;
  color: white;
}
</style>
