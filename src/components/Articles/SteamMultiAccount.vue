<template>
  <Article title="SteamMultiAccount" year="2015">
    <p class="col-md-10">
      In 2015 i have beautiful business plan of getting money from steam card system.
      <br>
      <br>How steam card system work:
      <ul>
        <li> In certain games you get cards every few hours after 3 hours of playing.</li>
        <li>
          This cards can be sold in steam community market
          (other people can earn experience for steam profile by collecting them)
        </li>
        <li>
          In time of steam sales there is many games with such low price,
          so cards from them can worth more.
        </li>
      </ul>
      So, it's basicly a complex and low value investment, but back in the days i was
      a high school student with no money, so it's was pretty much for me to buy
      beautiful, nasty, juicy, skins for my lovely SSG in CS:GO.
    </p>
    <p class="col-md-5">
      Plan was easy.<br>
      1. Create few accounts.<br>
      2. Buy games on steam sale.<br>
      3. Farm cards, and sell it.<br>
      4. ...<br>
      5. Profit.<br>
    </p>
    <div class="col-md-12">
      <img src="../../assets/snatch2.png" alt="My plan">
    </div>
    <p class="col-md-10">
      But do it by my hands i didn't want, so i start searching for existing
      solutions, and find <a href="https://github.com/JustArchiNET/ArchiSteamFarm" target="_blank">one</a>, pretty good, but not good enough for me.
      So, i start my own project from scratch guided by source code i found.
    </p>
    <MacOsWindow title="SteamMultiAccount">
      <img
        src='../../assets/steammultiaccount_first.png'
        alt="SteamMultiAccount"
        class="padding"
      >
    </MacOsWindow>
    <p class="col-md-10">
      Available features:
      <ul>
        <li>Loging with two factor authentication</li>
        <li>Farming cards from multiple account simultaneously</li>
        <li>Selling cards with median price from market</li>
      </ul>
    </p>
    <p class="col-md-10">
      At some moment Steam block idling of few games simultaneously,
      so, now there is two types of idling:
      <ul>
        <li>Simultaneously farming games to overcome 3hr limit</li>
        <li>Separate idling of game which already have 3hr</li>
      </ul>
      Farming games by downloading it and oppening is very expensive for
      network, processor and memory resources especially when it comes to idling of
      few games simultaneously. So, for this reason was created binary, which can emulate
      any game, by operating with C# wrapper of steamworks.
    </p>
  </Article>
</template>

<script>
import MacOsWindow from '../MacOsWindow.vue';
import Article from '../Article.vue';

export default {
  name: 'SteamMultiAccount',
  components: {
    MacOsWindow,
    Article,
  },
};
</script>

<style lang="scss" scoped>
img {
  width: 100%;
}
ul {
  margin-top: 1em;
  li {
    margin-top: 0.5em;
  }
}
a {
  font-weight: normal;
}
</style>
