<template>
  <div class="row text justify-content-center">
    <div class="header">
      <span class="title">{{ title }}</span>
      <span class="year">{{ year }}</span>
    </div>

    <slot />
  </div>
</template>

<script>
export default {
  name: 'Article',
  props: {
    title: String,
    year: String,
  },
};
</script>

<style lang="scss" scoped>
@import '../scss/vars.scss';
p {
  margin-top: 2em;
}
.header {
  margin-bottom: 40px;
  text-align: center;
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
ul {
  margin-top: 1em;
  li {
    margin-top: 0.5em;
  }
}
</style>
