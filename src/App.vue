<template>
  <h1>{{ title }}</h1>
  <div class="">
    <input type="text" ref="name" />
    <button @click="handleClick">click me</button>
  </div>
  <div class="" v-if="showModal">
    <ModalVue
      title="Hello World"
      content="lorem10013010230213asdawq sdad"
      @close="closeModal"
    >
      <h1>Title</h1>
      <p>Content</p>
      <template v-slot:links>
        <a href="#">Link 1</a>
        <a href="#">Link 2</a>
      </template>
    </ModalVue>
  </div>
  <button @click="openModal">Open Modal</button>
</template>

<script>
import ModalVue from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    ModalVue,
  },
  data() {
    return {
      title: "Hello world",
      showModal: false,
    };
  },
  methods: {
    handleClick() {
      this.$refs.name.focus();
    },

    openModal() {
      this.showModal = true;
    },

    closeModal() {
      this.showModal = false;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid;
  padding: 20px;
}
</style>
