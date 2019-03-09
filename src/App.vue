<template>
  <div id="app">
    <h1 class="name">TLD.party 🎉</h1>
    <h2 class="tagline">There are 1000+ fucking TLD’s in the world.</h2>
    <main class="wrapper">
      <TLD msg="Welcome to Your Vue.js App" />
    </main>
  </div>
</template>

<script>
import TLD from './components/TLD.vue'

export default {
  name: 'app',
  components: {
    TLD
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Dosis:400,500,700,800');

#app {
  font-family: 'Dosis', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #f9f9f9;
  margin-top: 90px;
  color: #4b4b4b;
}

.name {
  font-weight: bold;
  font-size: 54px;
  color: #4b4b4b;
  letter-spacing: 0;
  text-align: center;
  margin-bottom: 30px;
}
.tagline {
  font-weight: 500;
  font-size: 44px;
  color: #4b4b4b;
  letter-spacing: 0;
  text-align: center;
}

.wrapper {
  margin: auto;
  max-width: 500px;
}
</style>
