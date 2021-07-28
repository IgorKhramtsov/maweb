<template>
  <section class='header container-fluid'>
    <div class="hello container">
      <span>hi 👋</span>
      <span>my name is Igor</span>
      <span class="small">i am a software engineer</span>
      <span class="smallest">based in barnaul, russia</span>
      <img class="moloko" src="../assets/milk.png" alt="milk">
    </div>
  </section>
</template>

<script>
export default {
  name: 'Ahoj',
};
</script>

<style scoped lang="scss">
@import '../scss/vars.scss';

.hello {
  margin: auto;
  padding-top: 80px;
  span {
    display: block;
    color: $text-color-light;
    font-style: normal;
    font-weight: normal;
    font-size: 36px;
    line-height: 42px;
    ~.small {
      font-style: normal;
      font-weight: normal;
      font-size: 24px;
    }
    ~.smallest {
      font-style: normal;
      font-weight: 300;
      font-size: 22px;
    }
  }
}
.header {
  mask: url('../assets/toptop.svg');
  mask-repeat: no-repeat;
  mask-size: auto 590px;
  mask-position: center top;
  background-image: url('../assets/noise.png');
  background-color: $background-color-light;
  height: 90vh;
}
.moloko {
  position: absolute;
  top: 10px;
  right: 10px;
  height: 45px;
}
</style>
