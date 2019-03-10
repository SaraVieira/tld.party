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
@import url('./css/reset.css');

#app {
  font-family: 'Dosis', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
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

.tooltip {
  display: block !important;
  z-index: 10000;
  font-family: 'Dosis', Helvetica, Arial, sans-serif;
  color: #4b4b4b;

  .tooltip-inner {
    background: black;
    color: white;
    border-radius: 4px;
    padding: 5px 10px 4px;
    max-width: 400px;
    line-height: 1.3;
  }

  .tooltip-arrow {
    width: 0;
    height: 0;
    border-style: solid;
    position: absolute;
    margin: 5px;
    border-color: black;
    z-index: 1;
  }

  &[x-placement^='top'] {
    margin-bottom: 5px;

    .tooltip-arrow {
      border-width: 5px 5px 0 5px;
      border-left-color: transparent !important;
      border-right-color: transparent !important;
      border-bottom-color: transparent !important;
      bottom: -5px;
      left: calc(50% - 5px);
      margin-top: 0;
      margin-bottom: 0;
    }
  }

  &[x-placement^='bottom'] {
    margin-top: 5px;

    .tooltip-arrow {
      border-width: 0 5px 5px 5px;
      border-left-color: transparent !important;
      border-right-color: transparent !important;
      border-top-color: transparent !important;
      top: -5px;
      left: calc(50% - 5px);
      margin-top: 0;
      margin-bottom: 0;
    }
  }

  &[x-placement^='right'] {
    margin-left: 5px;

    .tooltip-arrow {
      border-width: 5px 5px 5px 0;
      border-left-color: transparent !important;
      border-top-color: transparent !important;
      border-bottom-color: transparent !important;
      left: -5px;
      top: calc(50% - 5px);
      margin-left: 0;
      margin-right: 0;
    }
  }

  &[x-placement^='left'] {
    margin-right: 5px;

    .tooltip-arrow {
      border-width: 5px 0 5px 5px;
      border-top-color: transparent !important;
      border-right-color: transparent !important;
      border-bottom-color: transparent !important;
      right: -5px;
      top: calc(50% - 5px);
      margin-left: 0;
      margin-right: 0;
    }
  }

  &.popover {
    $color: #fff;

    .popover-inner {
      background: $color;
      color: #4b4b4b;
      padding: 24px;
      box-shadow: 0 5px 30px rgba(black, 0.1);
    }

    .popover-arrow {
      border-color: $color;
    }
  }

  &[aria-hidden='true'] {
    visibility: hidden;
    opacity: 0;
    transition: opacity 0.15s, visibility 0.15s;
  }

  &[aria-hidden='false'] {
    visibility: visible;
    opacity: 1;
    transition: opacity 0.15s;
  }
}
</style>
