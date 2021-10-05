<template>
  <Article title="Arkanoid" year="2020" repoUrl="http://github.com/IgorKhramtsov/Arkanoid">
    <p class="col-md-10">
      Test assignment for Zefir Games. The task was to made simple clone of
      Arkanoid (breakout) game, on C++ and pure OpenGL. On that moment, i had
      pretty weak knowledge of OpenGL, but with help of videos from
      <a class="safarifix" href="https://www.youtube.com/playlist?list=PLlrATfBNZ98foTJPJ_Ev03o2oq3-GGOS2" target="_blank"> Cherno youtube channel</a> on OpenGL, I've successfully created a playable
      version after 4 days of developing.
    </p>
    <div class="col-md-10">
      <MacOsWindow title="Arkanoid">
        <video
          src="../../assets/arkanoid.mp4"
          alt="Gameplay"
          class="gif"
          autoplay="true"
          loop="true"
          playsinline="true"
          type="video/mp4"
        />
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
  margin-bottom: -6px;
}
a {
  font-weight: 300;
  &.safarifix {
    display: inline-block;
  }
}
</style>
