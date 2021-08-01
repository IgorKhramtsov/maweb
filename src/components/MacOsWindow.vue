<template>
  <div class="macoswindow">
    <div class="header">
      <div class="circle" style="background-color: #fc5b57"/>
      <div class="circle" style="background-color: #e5bf3c"/>
      <div class="circle" style="background-color: #57c038"/>
      <span class="title">{{ title }}</span>
    </div>
    <div class="content">
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  name: 'MacOsWindow',
  props: {
    title: String,
  },
};
</script>

<style lang="scss">
@import '../scss/vars.scss';

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
    background-color: $disabled-item;
    height: 4px;
    width: 100%;
  }
}
</style>

<style lang="scss" scoped>
.macoswindow {
  width: auto;
  margin-top: 2em;
  .content {
    background-color: #000000;
    border-radius: 0 0 8px 8px;
    border: 1.5px solid #2c2c2c;
    border-top: none;
  }
  .header {
    display: flex;
    position: relative;
    background-color: #292929;
    padding: 2px 0px;
    padding-left: 8px;
    padding-bottom: 10px;
    border-radius: 8px 8px 0 0;
    border: 1.5px solid #666666;
    border-bottom: none;
    .circle {
      width: 15px;
      height: 15px;
      border-radius: 15px;
      background-color: red;
      display: inline-block;
      margin: 0 4px;
      margin-top: 4px;
    }
    .title{
      display: inline-block;
      width: 100%;
      text-align: center;
      position: absolute;
      left: 0;
      color: #9e9e9e;
      font-weight: normal;
      font-size: 18px;
      // top: 0;
    }
  }
}

// For tablets (where timeline and article in 1 row)
@media(max-width: 990px) { // euristic number
  .macoswindow {
    img, iframe {
      max-width: 490px; // euristic number
    }
  }
}

// For mobile (where timiline and artivle in 2 rows)
@media(max-width: 530px) { // euristic number
  .macoswindow {
    img {
      width: 100%;
    }
    iframe {
      max-width: 100%;
    }
    .photoframe {
      width: inherit;
    }
  }
}

// disable macos circle on small screens
@media(max-width: 470px) { // euristic number (based on last video in SZOHack)
  .macoswindow {
    .header {
      min-height: 35px;
      .circle {
        display: none;
      }
    }
  }
}
</style>
