<script setup>

</script>

<template>
  

  <main>
    <h1>{{ title }}</h1>
    <div v-if="showModal">
      <Modal  :theme="sale" @close="toggleModal">
        <template v-slot:links>
          <a href="#">sign up now</a>
          <a href="#">more info</a>
        </template>
        <h1>ninja giveaway</h1>
        <p>grab your swag</p>
      </Modal>
    </div>


    <div v-if="showModalTwo">
      <Modal   @close="toggleModalTwo">
        <h1>sign up to the newsletter</h1>
        <p>fuck you!</p>
      </Modal>
    </div>
    <button @click="toggleModal">Open modal</button>
    <button @click="toggleModalTwo">Open modal</button>
  </main>
</template>

<script>
import Modal from "./components/Modal.vue"

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'my First vue app :)',
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    },
  }
}
</script>

<style scoped>
header {
  line-height: 1.5;
}

h1 {
  color: red;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
