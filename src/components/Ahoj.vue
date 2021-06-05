<template>
  <section class='header container-fluid'>
    <div class="hello container">
      <span>hi 👋</span>
      <span>my name is Igor</span>
      <span class="small">i am a software developer</span>
      <span class="smallest">currenlty located at barnaul, russia</span>
      <img class="moloko" src="../assets/milk.svg" alt="milk">
    </div>
  </section>
</template>

<script>
export default {
  name: 'Ahoj',
};
</script>

<style scoped lang="scss">
.hello {
  margin: auto;
  padding-top: 80px;
  span {
    display: block;
    color: #252525;
    font-style: normal;
    font-weight: normal;
    font-size: 36px;
    line-height: 42px;
    // margin-bottom: 3px;
    ~.small {
      font-style: normal;
      font-weight: normal;
      font-size: 24px;
      // line-height: 28px;
    }
    ~.smallest {
      font-style: normal;
      font-weight: 300;
      font-size: 22px;
      // line-height: 26px;
    }
  }
}
.header {
  mask: url('../assets/toptop.svg');
  mask-repeat: no-repeat;
  mask-size: auto 590px;
  mask-position: center top;
  background-image: url('../assets/noise.png');
  background-color: #E2E2E2;
  height: 90vh;
}
.moloko {
  position: absolute;
  top: 10px;
  right: 10px;
  transform: rotate(-3deg);
  height: 46px;
}
</style>
