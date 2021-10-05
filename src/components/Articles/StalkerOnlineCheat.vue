// TODO: rewrite slider

<template>
  <Article title="SZOHack" year="2012"
           :repos="[{
             text: 'second version',
             href: 'http://github.com/IgorKhramtsov/SZOHack-v2'
           },{
             text: 'third version',
             href: 'http://github.com/IgorKhramtsov/SZOHack-v3'
           }]">
    <p class="col-md-10">
      Back in 2012, when I was 15, I've been playing with Cheat&nbsp;Engine,
      scrolling through some cheat forum, and occasionally
      find article describing process of making auto-injectable
      cheat by replacing d3d9.dll, with source code
      attached. <br>
    </p>
    <p class="col-md-10">
      From that moment I spent some weeks trying
      to undestarnd how to apply this to game I've been playing at
      those time, without any clue how programming work at all,
      except knowledge about data structuring, I've get from playing
      with Cheat&nbsp;Engine. <br>
    </p>
    <div class="photoframe">
      <MacOsWindow title="second version of SZOHack">
        <img
          :src="getImgUrl(szohack_v2.images[szohack_v2.selected_image])"
          alt="second version of SZOHack"
        >
      </MacOsWindow>
      <div class="row justify-content-center">
        <div
          v-for="i in szohack_v2.images.length" :key="i"
          :class="'image_selector ' + (szohack_v2.selected_image == i -1 ? 'active' : '')"
          @click="szohack_v2.selected_image = i -1"
        />
      </div>
    </div>
    <p class="col-md-10">
      After a while, with help of some people from the same
      forum, I've succesfully config, build and run my
      frankestein-cheat, and start enhancing it, with memhack functions.<br>
    </p>
    <p class="col-md-10">
      I've should say thanks to developer team of this game,
      because if they have any anti-cheat system at that time,
      I've never been able to build this cheat, and find my passion
      for programming. <br>
    </p>
    <div class="photoframe">
      <MacOsWindow title="third version of SZOHack">
        <img
          :src="getImgUrl(szohack_v3.images[szohack_v3.selected_image])"
          alt="second version of SZOHack"
          class="padding"
        >
      </MacOsWindow>
      <div class="row justify-content-center">
        <div
          v-for="i in szohack_v3.images.length" :key="i"
          :class="'image_selector ' + (szohack_v3.selected_image == i -1 ? 'active' : '')"
          @click="szohack_v3.selected_image = i -1"
        />
      </div>
    </div>
    <p class="col-md-10">
      Back in the days, I was naive little boy, and got offer
      to sell my cheat through... lets name it 'publisher'. Of course
      I agree, and after dialog in Skype sent them special version
      of dll with changed author, and without hardware linking.
      Even today you can find some videos, posts and images
      of people trying to sell this, first, version of cheat.
    </p>
    <div class="photoframe video">
      <MacOsWindow title="leaked first version of cheat">
        <iframe
          class="video"
          width="560"
          height="315"
          src="https://www.youtube-nocookie.com/embed/IkonXJIdcwY"
          title="YouTube video player"
          frameborder="0"
          allow="accelerometer;
          autoplay;
          clipboard-write;
          encrypted-media;
          gyroscope;
          picture-in-picture"
          allowfullscreen
        />
      </MacOsWindow>
    </div>
  </Article>
</template>

<script>
import MacOsWindow from '../MacOsWindow.vue';
import Article from '../Article.vue';

export default {
  components: {
    MacOsWindow,
    Article,
  },
  Name: 'StalkerOnlineCheat',
  data() {
    return {
      szohack_v2: {
        selected_image: 0,
        images: [
          'szohack_v2_visual_menu.png',
          'szohack_v2_other_menu.png',
        ],
      },
      szohack_v3: {
        selected_image: 0,
        images: [
          'szohack_v3_visual_menu.png',
          'szohack_v3_other_menu.png',
          'szohack_v3_teleport_menu.png',
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
@import '../../scss/vars.scss';

.video {
  width: 560px;
}
.photoframe {
  width: auto;
  margin-top: 2em;
  .padding {
    padding: 16px;
  }
  span {
    text-align: center;
    display: block;
    font-weight: 100;
    width: 100%;
    font-size: 22px;
  }
}
</style>
