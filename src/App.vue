<template>
  <h1>{{ title }}</h1>
  <p>welcome...</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign Up Now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Giveway</h1>
      <p>Grab it befor late!</p>
    </Modal>
  </div> 

   <div v-if="showModalTwo">
    <Modal theme="sale" @close="toggleModalTwo">
      <h1>Sign up to the newsletter</h1>
      <p>For updates and promos</p>
    </Modal>
  </div> 
  <button @click.alt="toggleModal">open Modal(alt)</button>
  <button @click.alt="toggleModalTwo">open Modal Two(alt)</button>

</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  data() {
    return {
      title: 'My First Vue App :)',
      showModal: false,
      showModalTwo: false
    }
  },
  components: {
    Modal
  },
  methods : {
    handleClick() {
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
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
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
