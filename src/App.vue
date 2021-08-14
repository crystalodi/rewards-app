<template>
  <Header/>
  <div class="container">
    <router-view :prizes="prizes"></router-view>
  </div>
  <Footer/>
</template>

<script>
import "bootstrap/dist/css/bootstrap.min.css";
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

