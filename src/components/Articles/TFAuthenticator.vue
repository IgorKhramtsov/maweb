<template>
  <Article title='2FAuthenticator' year='2016'>
    <p class="col-md-10">
      While i was a poor high school student, i didn't have good phone, but i needed a way
      to use Steam two factor authentication. So i make some research, didn't find anything
      usefull at that moment, and start creating it by myself.
    </p>
    <div class="photoframe">
      <MacOsWindow title="2FAuthenticator">
        <img
          :src="getImgUrl(screenshots.images[screenshots.selected_image])"
          alt="Authenticator preview"
        >
      </MacOsWindow>
      <div class="row justify-content-center">
        <div
          v-for="i in screenshots.images.length" :key="i"
          :class="'image_selector ' + (screenshots.selected_image == i -1 ? 'active' : '')"
          @click="screenshots.selected_image = i -1"
        />
      </div>
    </div>
    <p class="col-md-10">
      Available features:
      <ul>
        <li>Logging into steam account</li>
        <li>Linking and removing 2FA</li>
        <li>Exporting and importing 2FA key profile</li>
        <li>Locking with 4 digits secret code</li>
        <li>Accepting multiple market sell pendings</li>
      </ul>
    </p>
    <p class="col-md-10">
      A few words about locking. Data in generated 2FA profile is encrypted.
      Encryption is pretty simple, but here is a trick. Every entered code is valid, and
      get you into main screen, but only correct secret code will get you correct 2FA codes.
      So it's make it difficult to bruteforce the secret code.
    </p>
  </Article>
</template>

<script>
import MacOsWindow from '../MacOsWindow.vue';
import Article from '../Article.vue';

export default {
  name: 'TFAuthenticator',
  components: {
    MacOsWindow,
    Article,
  },
  data() {
    return {
      screenshots: {
        selected_image: 0,
        images: [
          '2fauthenticator_login.png',
          '2fauthenticator_linking.png',
          '2fauthenticator_main.png',
        ],
      },
    };
  },
  methods: {
    getImgUrl(pic) {
      // eslint-disable-next-line import/no-dynamic-require, global-require
      return require(`../../assets/${pic}`);
    },
  },
};
</script>

<style lang="scss" scoped>
.photoframe {
  width: auto;
  margin-top: 2em;
}
a {
  font-weight: normal;
}
</style>
