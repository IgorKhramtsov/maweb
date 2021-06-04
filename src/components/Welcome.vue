<template>
  <section class="welcome container">
    <span>welcome to my <span class="can-you-feel-the-love-tonight">space</span></span>
  </section>
</template>

<script>
export default {
  name: 'Welcome',
};
</script>

<style scoped lang="scss">
.welcome {
  text-align: center;
  color: #e2e2e2;
  span {
    display: inline;
    font-style: normal;
    font-weight: normal;
    font-size: 36px;
    line-height: 42px;
    margin-bottom: 8px;
    ~.small {
      font-style: normal;
      font-weight: normal;
      font-size: 24px;
      line-height: 28px;
    }
    ~.smallest {
      font-style: normal;
      font-weight: 300;
      font-size: 22px;
      line-height: 26px;
    }
  }
}
</style>
