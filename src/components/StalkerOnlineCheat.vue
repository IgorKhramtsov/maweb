// TODO: rewrite slider

<template>
  <div class="row text">
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
            class="image_selector"
            @click="szohack_v2.selected_image = i -1"
          />
        </div>
      </div>
      <p class="col-md-8">
        And after a while, with help of some people from the same
        forum, i have succesfully config, build and run my
        frankestein-cheat. <br>
      </p><div class="col-md-4"/>
      <div class="col-md-4"/>
      <p class="col-md-8 right">
        I've should say thanks to developer team of this game,
        because if they have any anti-cheat system at those time,
        i've never been able to run this, and find my passion
        to programming. <br>
      </p>
      <p class="col-md-8">
        Back in the days i was naive little boy, and get offering
        to sell my cheat through lets name it 'publisher'. Of course
        i agree, and after dialog in skype sent them special version
        of dll with changed author, and with disabled linking.
        From this and on, you can find some videos, posts and images
        of people selling this cheat.
      </p>
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
.text {
  font-size: 22px;
  .right {
    // text-align: right;
  }
  p {
    margin-bottom: 30px;
  }
}
.dummy {
  height: 100px;
}
.photoframe {
  width: auto;
  padding: 12px;
  padding-bottom: 16px;
  margin: 25px 0;
  border-radius: 6px;
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
    &::after {
      content: '';
      position: absolute;
      top: 8px;
      border-radius: 8px;
      left: 0;
      background-color: #4568DC;
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
