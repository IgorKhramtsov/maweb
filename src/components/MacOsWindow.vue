<template>
  <div class="macoswindow">
    <div class="header">
      <div class="circle" style="background-color: #fc5b57"/>
      <div class="circle" style="background-color: #e5bf3c"/>
      <div class="circle" style="background-color: #57c038"/>
      <span class="title">{{title}}</span>
    </div>
    <div class="content">
      <slot/>
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

<style lang="scss" scoped>
.macoswindow {
  .content {
    background-color: #000000;
    border-radius: 0 0 8px 8px;
    border: 1.5px solid #2c2c2c;
    border-top: none;
  }
  .header {
    position: relative;
    background-color: #292929;
    padding: 2px 0px;
    padding-left: 8px;
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
</style>
