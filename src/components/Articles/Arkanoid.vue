<template>
  <Article title="Arkanoid" year="2020" repoUrl="http://github.com/IgorKhramtsov/Arkanoid">
    <p class="col-md-10">
      Test assignment for Zefir Games. The task was to made simple clone of
      Arkanoid (breakout) game, on C++ and pure OpenGL. On that moment, i had
      pretty weak knowledge of OpenGL, but with help of videos from
      <a href="https://www.youtube.com/playlist?list=PLlrATfBNZ98foTJPJ_Ev03o2oq3-GGOS2" target="_blank"> Cherno youtube channel on OpenGL</a>, i've successfully created a playable
      version after 4 days of developing.
    </p>
    <div class="col-md-10">
      <MacOsWindow title="Arkanoid">
        <video
          src="../../assets/arkanoid.webm"
          alt="Gameplay"
          class="gif"
          autoplay="true"
          loop="true"
        >
          <source ref="../../assets/arkanoid.webm">
          <source ref="../../assets/arkanoid.mov">
        </video>
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
}
</style>
