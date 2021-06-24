<template>
  <Article title="Starbound clone draft" year="2014">
    <p class="col-md-10">
      In summer holidays i was playing with Unity and start creating of
      Starbound clone (because it has interesting mechanics, i like to learn, and
      i love playing it in those days). I implement block placing and desctruction,
      basic inventory system, map generation by Perlin noise and water simulation.
      After that summer project was successfully abandoned.
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
      Perfomance is poor, but it is realy raw development build,
      and i didn't have so much experience in those time to make it right.
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
