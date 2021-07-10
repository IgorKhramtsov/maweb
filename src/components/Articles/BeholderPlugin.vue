<template>
  <Article title="Beholder android plugin" year="2019">
    <p class="col-md-10">
      In time of my internship at Alawar, they make port of their game Beholder 2 to mobile devices,
      so, i work on android plugin, which they used for around 10 years, but dont
      have a time to fix and enchance it. This plugin responsible for downloading game assets
      on first run. The game itself is made on Unity, and plugin is written
      in native Java code, which called from Unity via JNI.
      I rewrote it almost from scratch (it not so big by the way), because there was a lot
      of code, which deprecated and doesnt used. One of new features after rewriting was ability
      to continue downloading after reopening the game.
    </p>
  </Article>
</template>

<script>
import Article from '../Article.vue';

export default {
  name: 'BeholderPlugin',
  components: {
    Article,
  },
};
</script>

<style lang="scss" scoped>
.gif {
  width: 100%;
  margin-bottom: -1px;
}
</style>
