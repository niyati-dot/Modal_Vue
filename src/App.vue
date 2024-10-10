<template>
  <h1>{{ title }}</h1><br>
  <teleport to="#modals" v-if="showModal">
    <!-- <Modal :header="header" :text="text" theme="sale" @close="toggelModal" /> -->
    <Modal theme="" @close="toggelModal">
      <template v-slot:links>
        <a href="#" class="default">Sign Up</a>
        <a href="#" class="default">More Info</a>
      </template>
      <h1>Ninja Giveaway!</h1>
      <p>Grab Your ninja swag for half price!</p>
    </Modal>
  </teleport>
  <teleport to="#modals" v-if="showModalTwo">
    <Modal @close="toggelModalTwo">
      <h1>Sign Up to the Newsletter</h1>
      <p>For Updates and Promo Codes!</p>
    </Modal>  
  </teleport>
  <button @click="toggelModal" class="btn">Open Modal </button>
  <button @click="toggelModalTwo" class="btn">Open New Modal </button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  name: 'App',
  data(){
    return{
      title: 'My Vue App',
      header: 'Sign up for the Fiveway!',
      text: 'Grab your ninja swag for half price!',
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    toggelModal() {
      this.showModal = !this.showModal
    },
    toggelModalTwo() {
      this.showModalTwo = !this.showModalTwo
    }
  }
}
</script>

<style>
#app, #modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #eee;
  display: inline-block;
  padding-bottom: 10px;
}
a.default {
    padding: 10px;
    background-color: #7e1010;
    color: white;
    border-radius: 10px;
    margin: 10px;
    text-decoration: none;
}
</style>
