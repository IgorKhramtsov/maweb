<template>
  <Article title="Beholder android plugin" year="2019">
    <p class="col-md-10">
      In time of my internship at Alawar, they was porting their game «Beholder 2»
      to mobile devices.
      I was working on android plugin, they been using for around 10 years, but dont
      have a time to fix and enchance it. This plugin is responsible for downloading game assets
      on first run. The game itself is made on Unity, and plugin is written
      in native Java code, which called from Unity via JNI.
      I rewrote it almost from scratch (it's not so big by the way), because there was a lot
      of dead code. One of new features after rewriting is the ability
      to continue downloading after reopening the game from where it stops.
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
