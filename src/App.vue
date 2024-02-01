<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->

  <h1>{{ title }}</h1>

  <input type="text" ref="name" />
  <button @click="handleClick">Click</button>

  <teleport to="#modals" v-if="showModal">
    <!-- <ModalTest :header="header" :arr="[1,2,3,4]" theme="sale" @close="toggleModal" /> -->
    <ModalTest @close="toggleModal">
      <h1>Slot application</h1>
      <template v-slot:links>
        <p>slotted h1</p>
      </template>
    </ModalTest>
  </teleport>

  <teleport to="#modals" v-if="showModal2">
    <ModalTest @close="toggleModal2">
      <template v-slot:modal2>
        <p style="color: #111;">Modal 2</p>
      </template>
    </ModalTest>
  </teleport>




  <button @click="toggleModal">Show Modal</button>

  <button @click="toggleModal2">Show modal2</button>


</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import ModalTest from './components/ModalTest.vue'

export default {
  name: 'App',
  components: {
    ModalTest
  },
  data() {
    return {
      title: 'TEst tislt',
      header: 'Test my header',
      showModal: false,
      showModal2: false,
    }
  },
  methods: {
    handleClick() {
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2
    }

  }
}
</script>

<style>

#app, #modals {
 font-family: Consolas;
 margin: 0;
 padding: 0;
}


</style>
