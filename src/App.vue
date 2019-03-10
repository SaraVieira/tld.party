<template>
  <div id="app">
    <header>
      <ul>
        <li>Made by <a
            href="https://twitter.com/NikkitaFTW"
            target="_blank"
            rel="noopener noreferrer"
          >@NikkitaFTW</a></li>
        <li><a
            href="https://github.com/SaraVieira/tld.party"
            target="_blank"
            rel="noopener noreferrer"
          ><img
              width="25"
              src="./assets/github.svg"
            /></a></li>
      </ul>
    </header>

    <h1 class="name"><img
        alt="TLD.party"
        src="./assets/logo.svg"
        class="logo"
      /></h1>
    <h2 class="tagline">There a 1000+ fucking TLD’s in the world.</h2>
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
@import url('./css/reset.css');

#app {
  font-family: 'Dosis', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #f9f9f9;
  color: #4b4b4b;
}
.logo {
  max-width: 400px;
}
a {
  color: #6db0ff;
  text-decoration: none;

  &:hover {
    color: #4f84c0;
  }
}

header ul {
  margin-right: 60px;
  margin-top: 40px;
  display: flex;
  justify-content: flex-end;
  align-items: center;

  li:not(:last-child) {
    margin-right: 20px;
  }
}

.name {
  margin-top: 90px;
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
