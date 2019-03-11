<template>
  <section>
    <div class="top">
      <a
        :href="'https://icannwiki.org/' + tld.name.toLowerCase()"
        target="_blank"
      >
        <span>{{tld.name}}</span>
        <!-- {{JSON.stringify(tld)}} -->
      </a>
      <button v-on:click="open = !open">
        <img
          v-if="!open"
          width="30"
          src="../assets/down.svg"
          alt="show more"
        />
        <img
          v-if="open"
          width="30"
          src="../assets/up.svg"
          alt="show less"
        />
      </button>
    </div>
    <div
      class="open"
      v-if="open"
    >
      <p class="notes">{{tld.notes}}</p>
      <p v-if="tld.entity"><b>Entity: </b>{{tld.entity}}</p>
      <p v-if="tld.administrator"><b>Administrator: </b>{{tld.administrator}}</p>
      <div class="asides">
        <div
          v-tooltip.top-center="IDN"
          v-bind:class="{ exists: tld.IDN, square: true }"
        >IDN</div>
        <div
          v-tooltip.top-center="DNSSEC"
          v-bind:class="{ exists: tld.DNSSEC, square: true }"
        >DNSSEC</div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  props: ['tld'],
  data() {
    return {
      IDN:
        'Internationalized domain name provide a solution to the problem of handling umlauts and special characters. The Internet address in question is encoded in ASCII format. This step is also called normalization because the address is adapted to the ASCII standard.',
      DNSSEC:
        'The Domain Name System Security Extensions (DNSSEC) is a suite of Internet Engineering Task Force (IETF) specifications for securing certain kinds of information provided by the Domain Name System (DNS) as used on Internet Protocol (IP) networks.',
      open: false
    }
  }
}
</script>

<style lang="scss" scoped>
section {
  .top {
    display: flex;
    align-items: center;
    justify-content: space-between;

    button {
      border: none;
      background: transparent;
      color: inherit;
    }
  }

  .open {
    padding-bottom: 40px;
  }
  .notes {
    margin-top: 40px;
    margin-bottom: 20px;
  }
  p {
    b {
      font-weight: bold;
    }
    line-height: 1.3;
    margin: 5px;
  }

  a {
    text-decoration: none;

    span {
      font-weight: 800;
      font-size: 54px;
      color: #4b4b4b;
      letter-spacing: 0;
      text-align: center;
      position: relative;

      @media screen and (max-width: 700px) {
        font-size: 24px;
      }
      &:after {
        content: '';
        background: #6db0ff;
        box-shadow: 0 6px 12px 0 rgba(109, 176, 255, 0.2);
        border-radius: 3px;
        height: 4px;
        width: 100%;
        display: block;
        position: absolute;
        margin-top: 19px;
      }
    }
  }
}
.asides {
  display: flex;
  margin-top: 20px;
  .square {
    width: 60px;
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #da7e7e;
    margin-right: 20px;
    font-weight: 700;

    &.exists {
      background: #aada7e;
    }
  }
}
</style>
