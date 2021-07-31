<template>
  <div class="row text justify-content-center article">
    <div class="header" :style="{'margin-bottom': `${headerMargin}px`}">
      <span class="title">{{ title }}</span>
      <span class="year">{{ year }}</span>
    </div>
    <div v-if="repoUrl != null" class="buttons-array">
      <a :href="repoUrl" target="_blank" class="github-button">
        <span class="github-text">source code</span>
        <img
          src="../assets/icons/github.svg"
          alt="source code"
          class="github-icon"
        >
      </a>
    </div>
    <div v-else class="buttons-array">
      <a
        v-for="repo in repos"
        :key="repo.href"
        :href="repo.href"
        target="_blank"
        class="github-button margin"
      >
        <span class="github-text">{{ repo.text }}</span>
        <img
          src="../assets/icons/github.svg"
          alt="source code"
          class="github-icon"
        >
      </a>
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
    repos: Array,
    repoUrl: String,
  },
  computed: {
    headerMargin() {
      let margin = 40;
      if (this.repos != null) {
        margin += (this.repos.length - 1) * 24;
      }

      return margin;
    },
  },
};
</script>

<style lang="scss" scoped>
@import '../scss/vars.scss';
.article {
  position: relative;
}
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

.buttons-array {
  position: absolute;
  top: 70px;
  right: 5px;
}
.github-button {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  top: -20px;
  position: relative;
  @include disable-text-gradient;
  color: $text-color;
  text-decoration: none;
  &.margin {
    margin-bottom: 8px;
  }
  .github-text {
    font-weight: 200;
    margin: 0 12px;
  }
  .github-icon {
    height: 24px;
    width: 24px;
  }
}
</style>
