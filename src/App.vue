<template>
  <Header/>
  <div class="content">
    <router-view :prizes="prizes"></router-view>
  </div>
  <Footer/>
</template>

<script>
import Header from "./components/Header.vue"
import Footer from "./components/Footer.vue"
import {prizes} from "./fakeData";
export default {
  name: 'App',
  data() {
    return {
      prizes: []
    }
  },
  components: {
    Header,
    Footer
  },
  created () {
    this.getPrizes();
  },
  methods: {
    getPrizes() {
      this.prizes = prizes;
    }
  },
}
</script>

<style>
html, body {
  margin: 0;
  padding: 0;
  font-size: 100%;
  min-height: 100%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
.content {
  text-align: center;
  padding: 2.5em;
}
</style>
