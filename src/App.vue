<template>
  <Header/>
  <div class="content">
    <router-view></router-view>
  </div>
  <Footer/>
</template>

<script>
import Header from "./components/Header.vue"
import Footer from "./components/Footer.vue"

export default {
  name: 'App',
  components: {
    Header,
    Footer
  }
}
</script>

<style>
html, body {
  margin: 0;
  padding: 0;
  font-size: 100%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
.content {
  display: flex;
  flex-direction: row;
  justify-content: center;
  padding: 2.5em;
}
</style>
