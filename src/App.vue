<template>
  <div id="app">
    <div class="background-void">
      <div
        ref="bgf"
        class="background-first"
        :style="{ transform: `translate3d(0px, ${bgscroll}%, 0px)` }"
      />
      <div
        ref="bgs"
        class="background-second"
        :style="{ transform: `translate3d(0px, ${bgscroll / 1.5}%, 0px)` }"
      />
    </div>
    <Ahoj />
    <Welcome ref="welcomeref" />

    <About :internships="internships" />
    <Portfolio />

    <Contact />

    <Ending />
  </div>
</template>

<script>
import About from './components/About.vue';
import Ahoj from './components/Ahoj.vue';
import Welcome from './components/Welcome.vue';
import Ending from './components/Ending.vue';
import Portfolio from './components/Portfolio.vue';
import Contact from './components/Contact.vue';

export default {
  name: 'App',
  components: {
    Ahoj,
    Welcome,
    About,
    Ending,
    Portfolio,
    Contact,
  },
  data() {
    return {
      internships: [
        {
          name: 'IntegraSources',
          href: 'https://integrasources.com',
        },
        {
          name: 'Alawar',
          href: 'https://company.alawar.com/en/',
        },
        {
          name: 'Sibirix',
          href: 'https://sibirix.com',
        },
      ],
      bgscroll: 100.0,
    };
  },
  mounted() {
    document.addEventListener('scroll', this.handleScroll);
  },
  unmounted() {
    document.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      const { scrollY } = window;
      const height = document.body.offsetHeight;
      this.bgscroll = ((height - scrollY) / (height * 1.0)) * 100;
    },
  },
};
</script>

<style lang="scss">
@import './scss/vars.scss';

#app {
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: $text-color;
  overflow-x: hidden;
}
.background-void {
  height: 100%;
  width: 100%;
  display: block;
  position: fixed;
  background-color: $background-color;
  z-index: -1;
  div {
    width: 100%;
    height: 100%;
    transition: 0.2s transform ease-out;
  }
  .background-first {
    background-image: url('./assets/stars_big.svg');
  }
  .background-second {
    background-image: url('./assets/stars_small.svg');
  }
  &:before{
    z-index: 1;
    position: fixed;
    display: block;
    width: 100%;
    height: 100%;
    left: 0;
    top: 0;
    content: '';
  }
}
.can-you-feel-the-love-tonight {
  @include can-you-feel-the-love-tonight-text;
}
*::-webkit-scrollbar {
  width: 6px;
  background: $background-color;
  position: absolute;
}
*::-webkit-scrollbar-track-piece {
  background: transparent;
}
*::-webkit-scrollbar-track {
  background: transparent;
}
*::-webkit-scrollbar-corner {
  background: transparent;
}
*::-webkit-scrollbar-thumb {
  border-radius: 20px;
  @include can-you-feel-the-love-tonight;
}
a {
  @include can-you-feel-the-love-tonight-text;
}
</style>
