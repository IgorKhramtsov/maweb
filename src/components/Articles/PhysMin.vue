<template>
  <Article title="PhysMin" year="2020"
           :repos="[{
             text: 'android physmin',
             href: 'http://github.com/IgorKhramtsov/physmin-android'
           },{
             text: 'serverless physmin',
             href: 'http://github.com/IgorKhramtsov/physmin-functions'
           },{
             text: 'service website physmin',
             href: 'http://github.com/IgorKhramtsov/physmin-web'
           }]">
    <p class="col-md-10">
      My bachelor project, i've made with my group mate. Idea of app was inspired by Duolingo,
      with predominance of practice above the theory. Our physics professor gave
      us theoretical materials, to built app upon of them. The main idea was in a large amount
      of precedural generated task cases. So for this we create typescript "server" on firebase.
      To make sure, the generated tasks are correct (and this is very important in
      such applications) unit-tests was written, and run on every push via gitlab CI.
    </p>
    <div class="col-md-10">
      <img
        src="../../assets/physmin.gif"
        alt="Process of working with PhysMin app"
        class="appgif"
      >
    </div>
    <p class="col-md-10">
      Android app is written on kotlin, contains some custom views and layouts.
      Also had an lottie animation on end of test. To keep user data, firebase&nbsp;authentication
      with firestore was used. On wrong answer, task is moved to end of queue, so user have
      to complete all tests. For debug purpose i've implement simple helper which appear
      on top of screen, to tell is this answer is correct or not. Figma was used for designing UI.
    </p>
    <div class="col-md-10">
      <MacOsWindow title="Service website">
        <video
          src="../../assets/physmin-web.webm"
          alt="Service website functionality preview"
          class="gif"
          autoplay="true"
          loop="true"
        >
          <source ref="../../assets/physmin-web.webm">
          <source ref="../../assets/physmin-web.mov">
        </video>
      </MacOsWindow>
    </div>
    <p class="col-md-10">
      To make easier process of creating test sequences for each subject, service website
      was created with react and Material UI on firebase hosting. This site is operate with
      firestore database, for building configs, based on which the tests will be built on
      user request.
    </p>
  </Article>
</template>

<script>
import MacOsWindow from '../MacOsWindow.vue';
import Article from '../Article.vue';

export default {
  name: 'PhysMin',
  components: {
    MacOsWindow,
    Article,
  },
};
</script>

<style lang="scss" scoped>
.appgif {
  max-width: 350px;
  display: block;
  margin: auto;
}
.gif {
  width: 100%;
  margin-bottom: -6px;
}
</style>
