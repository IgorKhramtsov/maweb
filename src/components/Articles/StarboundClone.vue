<template>
  <Article title="Starbound clone draft" year="2014" repoUrl="http://github.com/IgorKhramtsov/starbound-clone-draft">
    <p class="col-md-10">
      At summer holidays, I was playing with Unity and begin to develop
      Starbound clone (because it has interesting mechanics, which I want to examine
      from the inside, and I love playing it in those days).
      I implement block placing and desctruction,
      basic inventory system, map generation by Perlin noise and water simulation.
      After that summer, project was successfully abandoned.
    </p>
    <div class="col-md-10">
      <MacOsWindow title="Starbound clone draft">
        <img
          src='../../assets/starboundclone.gif'
          alt="Starbound clone draft"
          class="gif"
        >
      </MacOsWindow>
    </div>
    <p class="col-md-10">
      Perfomance is not the best, but it is realy raw development build,
      and I didn't have so much experience in those time to make it right.
    </p>
  </Article>
</template>

<script>
import MacOsWindow from '../MacOsWindow.vue';
import Article from '../Article.vue';

export default {
  name: 'StarboundClone',
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
