<template>
  <section class="container">
    <div class="row center">
      <div class="row">
        <div class="col-md-12">
          <span class="header">contact me</span>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12">
          <span class="info">
            you can contact me by email at&nbsp;<a href="mailto:i@khramtsov.dev">i@khramtsov.dev</a>
            or via telegram&nbsp;<a href="https://t.me/vostmarkh" target="_blank">@vostmarkh</a>
          </span>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12">
          <img src="../assets/tardis_move.svg" alt="tardis">
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Contact',
  setup() {
  },
};
</script>

<style lang="scss" scoped>
.center {
  height: 70vh;
  padding-top: 35vh;
  align-content: center;
}
.header {
  font-size: 36px;
}
.info {
  margin: 2em 0;
  display: block;
  font-size: 24px;
}
img {
  display: block;
  margin: auto;
}
</style>
