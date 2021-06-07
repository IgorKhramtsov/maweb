// TODO: rewrite slider

<template>
  <div class="row text">
    <div class="header">
      <span class="title">stalker online cheat</span>
      <span class="year">2012</span>
    </div>
      <p class="col-md-8">
        Back in 2012 i've been playing with cheat&nbsp;engine,
        scrolling through some cheat forum, and occasionally
        find article describing process of making auto-injected
        cheat through replacing d3d9.dll, with source code
        attached. <br>
      </p>
      <div class="col-md-4"/>
      <div class="col-md-4"/>
      <p class="col-md-8 right">
        From this moment i've spent some weeks trying
        to undestarnd how to apply this to game i was play at
        those time, without any clue how programming work at all,
        except knowledge about data structuring, i've get from playing
        with cheat engine. <br>
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
      <p class="col-md-8">
        And after a while, with help of some people from the same
        forum, i have succesfully config, build and run my
        frankestein-cheat, and start to enhancing it, with memhack functions.<br>
      </p><div class="col-md-4"/>
      <div class="col-md-4"/>
      <p class="col-md-8 right">
        I've should say thanks to developer team of this game,
        because if they have any anti-cheat system at those time,
        i've never been able to build this cheat, and find my passion
        for programming. <br>
      </p>
      <div class="col-md-5"/>
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
      <p class="col-md-8">
        Back in the days i was naive little boy, and get offering
        to sell my cheat through lets name it 'publisher'. Of course
        i agree, and after dialog in skype sent them special version
        of dll with changed author, and with disabled linking.
        From this and on, you can find some videos, posts and images
        of people selling this first version of cheat.
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
            allowfullscreen/>
        </MacOsWindow>
        </div>
  </div>
</template>

<script>
import MacOsWindow from './MacOsWindow.vue';

export default {
  components: {
    MacOsWindow,
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
      return require(`../assets/${pic}`);
    },
  },
};
</script>

<style lang="scss" scoped>
@import '../scss/vars.scss';

.header {
  margin-bottom: 40px;
  text-align: right;
  position: relative;
  &::after {
    @include can-you-feel-the-love-tonight;
    position: relative;
    content: '';
    display: block;
    top: 7px;
    width: 100%;
    height: 2px;
  }
  .title {
    font-size: 36px;
  }
  .year {
    letter-spacing: 0.2em;
    font-size: 16px;
    position: absolute;
    top: -7px;
    margin-left: 5px;
  }
}
.video {
  width: 560px;
  margin: auto !important;
}
.text {
  font-size: 22px;
  p {
    margin-bottom: 30px;
  }
}
.photoframe {
  width: auto;
  margin: 25px 0;
  .padding {
    padding: 16px;
  }
  .image_selector {
    // tap area
    top: -5px;
    height: 20px;
    width: 20%;
    flex: 0 0 auto;
    margin: 0 8px;
    padding: 0;
    // background-color: black;
    cursor: pointer;
    position: relative;
    &.active {
      &::after {
        background-color: #B06AB3;
      }
    }
    &::after {
      content: '';
      position: absolute;
      top: 8px;
      border-radius: 8px;
      left: 0;
      background-color: rgba(55, 59, 68, 1);
      height: 4px;
      width: 100%;
    }
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
