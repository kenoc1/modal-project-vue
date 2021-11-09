<template>
  <div class="h-screen flex flex-col">
    <Navbar v-bind:links="['Home', 'About', 'Contact']" />

    <div class="mb-auto">
      <h1 class="text-6xl font-normal leading-normal mt-0 mb-2 text-pink-800">
        {{ title }}
      </h1>
      <p>Welcome...</p>
      <div v-if="showModal">
        <Modal theme="dark" @close="toggleModal">
          <template v-slot:links>
            <div>
              <a href="#">google</a>
              <a href="#">bing</a>
            </div>
          </template>
          <h4
            class="text-3xl font-normal leading-normal mt-0 mb-2 text-pink-800"
          >
            Login
          </h4>
          <p>asdfasdf</p>
        </Modal>
      </div>
      <div v-if="showModalTwo">
        <Modal theme="dark" @close="toggleModalTwo">
          <template v-slot:links>
            <div>
              <a href="#">google</a>
              <a href="#">bing</a>
            </div>
          </template>
          <h4
            class="text-3xl font-normal leading-normal mt-0 mb-2 text-pink-800"
          >
            Newsletter
          </h4>
          <p>asdfasdf</p>
        </Modal>
      </div>
      <div>
        <button
          class="
            bg-gray-500
            hover:bg-gray-400
            text-white
            font-bold
            py-2
            px-4
            m-4
            border-b-4 border-gray-700
            hover:border-gray-500
            rounded
          "
          @click="toggleModal"
        >
          open Modal
        </button>
        <button
          class="
            bg-gray-500
            hover:bg-gray-400
            text-white
            font-bold
            py-2
            px-4
            m-4
            border-b-4 border-gray-700
            hover:border-gray-500
            rounded
          "
          @click="toggleModalTwo"
        >
          open Modal Two
        </button>
      </div>
    </div>

    <Footer />
  </div>
</template>

<script>
import Modal from "./components/Modal.vue";
import Footer from "./components/Footer";
import Navbar from "./components/Navbar";

export default {
  name: "App",
  components: { Modal, Footer, Navbar },
  data() {
    return {
      title: "Modal Project",
      header: "Sign in for yeet",
      text: "........",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
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
  /* margin-top: 60px; */
}
</style>
