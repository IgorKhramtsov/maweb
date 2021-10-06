<template>
  <Article title="Devour" year="2021-currently" repoUrl="http://github.com/IgorKhramtsov/devour">
    <p class="col-md-10">
      My pet project, app for viewing memes, inspired by TikTok, where you have
      minimum useless space, concetrated on video and main goal is engage user for
      as long as possible. The project is still in active development, and currently have only
      reddit OAuth integration and TikTok-like feed page.
    </p>
    <div class="col-md-10">
      <video
        src="../../assets/devour.mp4"
        alt="Video of app"
        class="gif"
        autoplay="true"
        loop="true"
        playsinline="true"
        type="video/mp4"
      />
    </div>

    <p class="col-md-10">
      On this project I am trying out Domain Driven Design development approach, and
      use new libs, that I don't use on work project.
      <ul>
        <li> Database: Hive </li>
        <li> Network: Dio, Retrofit </li>
        <li> State managment: BLoC </li>
        <li> UI: Lottie, Rive </li>
        <li> Other: FPDart, GetIt, Freezed </li>
      </ul>
    </p>
  </Article>
</template>

<script>
import Article from '../Article.vue';

export default {
  name: 'Devour',
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
