<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->

  <h1>{{ title }}</h1>

  <input type="text" ref="name" />
  <button @click="handleClick">Click</button>

  <ModalTest :header="header" :arr="[1,2,3,4]" theme="sale"/>
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
      header: 'Test my header'
    }
  },
  methods: {
    handleClick() {
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    }
  }
}
</script>

<style>

#app {
 font-family: Consolas;
 margin: 0;
 padding: 0;
}


</style>
