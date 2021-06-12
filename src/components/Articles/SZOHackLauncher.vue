<template>
  <Article title='SZOHack launcher' year='2013'>
    <p class="col-md-10">
      For selling cheat, i've made, i had to create launcher
      for managing updates, securing linking method, by verifying
      computer datetime and injecting it into the game
      (from&nbsp;second version, cheat became not auto-injected,
      because developers start checking d3d9.dll).
    </p>
    <p class="col-md-10">
      So i create uCoz site for managing news and version
      updating, and develop WindowsForm app for everything else.
    </p>
    <div class="photoframe">
      <MacOsWindow title="SZOHack launcher">
        <img
            src='../../assets/szohack_launcher.png'
            alt="SZOHack launcher"
            class="padding"
          >
      </MacOsWindow>
    </div>
  </Article>
</template>

<script>
import MacOsWindow from '../MacOsWindow.vue';
import Article from '../Article.vue';

export default {
  components: {
    MacOsWindow,
    Article,
  },
  name: 'SZOHack',
};
</script>

<style lang="scss" scoped>
.photoframe {
  width: auto;
  margin-top: 2em;
  .padding {
    padding: 16px 46px;
  }
}
</style>
