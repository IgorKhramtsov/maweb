<template>
  <div id="app">
    <div class="background-void"/>
    <Ahoj/>
    <Welcome/>

    <About v-bind:internships="internships"/>
    <Portfolio/>

    <Ending/>
  </div>
</template>

<script>
import About from './components/About.vue';
import Ahoj from './components/Ahoj.vue';
import Welcome from './components/Welcome.vue';
import Ending from './components/Ending.vue';
import Portfolio from './components/Portfolio.vue';

export default {
  name: 'App',
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
    };
  },
  components: {
    Ahoj,
    Welcome,
    About,
    Ending,
    Portfolio,
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
}
.background-void {
  height: 100%;
  width: 100%;
  display: block;
  position: fixed;
  background-color: $background-color;
  z-index: -1;
  &:before{
    z-index: 1;
    position: fixed;
    display: block;
    width: 100%;
    height: 100%;
    left: 0;
    top: 0;
    content: '';
    background-image: url('./assets/sky_seamless.png');
    background-blend-mode: lighten;
    opacity: 0.35;
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
</style>
