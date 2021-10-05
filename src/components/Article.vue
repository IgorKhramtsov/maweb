<template>
  <div class="row text justify-content-center article">
    <div class="header" :style="{'margin-bottom': `${headerMargin * 1.3}em`}">
      <span class="title">{{ title }}</span>
      <span class="year">{{ year }}</span>
      <div class="buttons-array">
        <a
          v-for="repo in reposarray"
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
      let margin = 1;
      if (this.repos != null) {
        margin += (this.repos.length - 1);
      }

      return margin;
    },
    // Accessor for repos (use repoUrl if only 1 repo)
    reposarray() {
      if (this.repos != null) {
        return this.repos;
      }
      if (this.repoUrl != null && this.repoUrl !== undefined) {
        return [{
          text: 'source code',
          href: this.repoUrl,
        }];
      }
      return [];
    },
  },
};
</script>

<style lang="scss" scoped>
@import '../scss/vars.scss';
.article {
  position: relative;
  padding-top: 40px;
}
p {
  margin-top: 2em;
}
.header {
  padding-bottom: 40px;
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
  top: 75px;
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

// mobile (article inside of timeline)
@media(max-width: 767px) {
  .article {
    padding-top: 0;
    font-size: 19px;
    text-align: left;
    margin-bottom: 40px;
  }
  .header {
    padding-bottom: 0px;
    margin-bottom: 0px !important;
      .title, .year {
        display: none;
      }
      &:after {
        display: none;
      }
      .buttons-array {
        position: relative;
        top: 20px;
        text-align: left;
        a {
          justify-content: space-between;
          padding: 0 15px;
        }
      }
  }
}
</style>
