<template>
  <Article title="SingularityApp" year="2020-2021">
    <p class="col-md-10">
      In september of 2020, I start working as Flutter developer on SingularityApp.
      This is advanced ToDo, with clients app on all platforms. Until that day, I had
      no experience with Flutter, but got to grips with it pretty quickly. Especially i love to
      work with animations and optimizing performance with profiler.
    </p>
    <div class="col-md-10">
      <video
        src="../../assets/singularity.mp4"
        alt="Video of app"
        class="gif"
        autoplay="true"
        loop="true"
        playsinline="true"
        type="video/mp4"
      />
    </div>

    <p class="col-md-10">
      During my work, I acquired the following skills:
      <ul>
        <li> Connecting app to Firebase Analytics and Crashlytics </li>
        <li> Migrating to Embedding 2 (with libs) </li>
        <li> Migrating to Null-safety </li>
        <li> Working with native notifications </li>
        <li> Working with background jobs </li>
        <li> Writing unit-tests </li>
        <li> Writing documentation </li>
        <li> Working with user's and server's log files, for bugfixing </li>
        <li> Working with native android (and little bit of ios) widgets </li>
        <li> Writing custom native plugins </li>
        <li> Refactoring and permormance optimizing </li>
        <li> Adapting design to tablets </li>
        <li> Working with JSON </li>
        <li> Working with GitLab CI/CD </li>
        <li> Publishing releases to GooglePlay and Appstore </li>
      </ul>
    </p>
  </Article>
</template>

<script>
import Article from '../Article.vue';

export default {
  name: 'SingularityApp',
  components: {
    Article,
  },
};
</script>

<style lang="scss" scoped>
.gif {
  margin: auto;
  display: block;
  max-height: 600px;
  border-radius: 45px;
}
</style>
