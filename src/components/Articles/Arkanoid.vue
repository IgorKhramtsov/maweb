<template>
  <Article title="Arkanoid" year="2020">
    <p class="col-md-10">
      Test assignment for Zefir Games. The task was to made simple clone of
      Arkanoid (breakout) game, on C++ and pure OpenGL. On that moment, i have
      pretty weak knowledge of OpenGL, but with help of videos from
      Cherno youtube channel on OpenGL, i've successfully made a playable
      version after 4 days of developing.
    </p>
    <div class="col-md-10">
      <MacOsWindow title="Arkanoid">
        <img
          src="../../assets/arkanoid.gif"
          alt="Gameplay"
          class="gif"
        >
      </MacOsWindow>
    </div>
  </Article>
</template>

<script>
import MacOsWindow from '../MacOsWindow.vue';
import Article from '../Article.vue';

export default {
  name: 'Arkanoid',
  components: {
    MacOsWindow,
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
