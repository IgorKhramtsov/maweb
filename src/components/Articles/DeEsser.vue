<template>
  <Article title="DeEsser" year="2020" repoUrl="http://github.com/IgorKhramtsov/DeEsser">
    <p class="col-md-10">
      Bachelor's audio processing project for getting rid of excessive prominence of
      sibilant consonants.
      While recording sound from cheap recorder, like smartphone, resulting audio often contains
      unpleasant, harsh, sound of sibilant consonants. Developed algorithm searches for excessive
      sibilants in audio by counting number of zero crossing on each area, and apply filter on
      areas, where counted number is greater than certain constant. Filter itself is converting
      each area by Fast Fourier Transform, then suppress intensity of frequencies above certain
      threshold and converts signal back by Inverse Fast Fourier Transform.
    </p>
    <div class="col-md-10">
      <MacOsWindow title="DeEsser">
        <img
          src="../../assets/deesser.jpg"
          alt="Program interface"
        >
      </MacOsWindow>
    </div>
    <p class="col-md-10">
      Resulted program have two presets for male and female vocals, two inputs for tuning
      detector threshold and intense of suppression. Interface created with NanoGUI
      and audio signal is rendered on canvas by shaders, with ability to zoom and move around.
    </p>
  </Article>
</template>

<script>
import Article from '../Article.vue';
import MacOsWindow from '../MacOsWindow.vue';

export default {
  name: 'DeEsser',
  components: { MacOsWindow, Article },
};
</script>

<style lang="scss" scoped>
img {
  width: 100%;
}
</style>
