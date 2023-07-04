<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <!-- <img @click="increment()" :src="fullPath" /> -->
  <img  @click="increment()" v-if="currentIndex == 0" src="./assets/dradis.gif" />
  <img  @click="increment()" v-else-if="currentIndex == 1" src="./assets/xwing.gif" />
  <img  @click="increment()" v-else-if="currentIndex == 2" src="./assets/collision.gif" />
  <img  @click="increment()" v-else-if="currentIndex == 3" src="./assets/lacaille.gif" />
  <img  @click="increment()" v-else-if="currentIndex == 4" src="./assets/mech.gif" />
  <img  @click="increment()" v-else-if="currentIndex == 5" src="./assets/toxic.gif" />
  <img  @click="increment()" v-else-if="currentIndex == 6" src="./assets/terminal.gif" />
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data(){
    return {
      currentIndex: 0,
      gifs: [
        'dradis',
        'xwing',
        'xwing',
        'xwing',
        'xwing',
        'xwing',
        'xwing',
        'xwing',
      ]
    }
  },
  methods: {
    increment(){
      this.currentIndex++;

      if(this.currentIndex > this.gifs.length - 1){
        this.currentIndex = 0;
      }
    },
    decrement(){
      this.currentIndex--;

      if(this.currentIndex < 0){
        this.currentIndex = this.gifs.length - 1;
      }
    }
  },
  computed: {
    fullPath(){
      return `./assets/img/${this.gifs[this.currentIndex]}.gif`
    }
  }
}
</script>

<style>
body {
  margin: 0px;
}
#app {
  align-items: center;
  background-color: #222;
  display: flex;
  justify-content: center;
  height: 100vh;
  width: 100vw;
  margin: 0px;
}
img {
  width: 100vw;
}
</style>
