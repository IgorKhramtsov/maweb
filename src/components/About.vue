<template>
  <section class="container">
    <div class="about">
      <div class="row">
        <p>
          started coding at 15, made a few personal projects,
          <br>and successfully get the Bachelor’s degree.
        </p>
      </div>
      <div class="row">
        <p class="internships">
          complete internship at
          <span v-for="i in internships.length" :key="i">
            <a :href="internships[i-1].href" target="_blank">{{internships[i-1].name}}</a>
            <span>{{i == internships.length - 1 ? ' and ' : i == internships.length ? "." : ", "}}
            </span>
          </span>
        </p>
      </div>
      <div class="row justify-content-center">
        <div class="col-md-8 experience">
          <p>have experience with:</p>
          <ul>
            <li>C# windows form</li>
            <li>gamedev (also hacking games)</li>
            <li>web development</li>
            <li>native and flutter mobile development</li>
            <li>backend development</li>
            <li>openCV</li>
            <li>firebase</li>
          </ul>
        </div>
      </div>
      <div class="row">
        <p>
          currently working on <a href="https://singularity-app.com" target="_blank">SingularityApp</a> at Sibirix as Flutter developer.
        </p>
      </div>
    </div>
    <img
      src="../assets/planet_1.svg"
      alt="planet"
      :style="{ transform: `translate3d(0px, ${scroll}%, 0px)` }"
    >
  </section>
</template>

<script>
export default {
  name: 'About',
  props: {
    internships: Array,
  },
  data() {
    return {
      scroll: 0.0,
    };
  },
  mounted() {
    document.addEventListener('scroll', this.handleScroll, { passive: true });
  },
  unmounted() {
    document.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      const { scrollY } = window;
      const height = document.body.offsetHeight;
      this.scroll = -100 + ((height - scrollY) / (height * 1.0)) * 100;
    },
  },
};
</script>

<style scoped lang="scss">
@import '../scss/vars.scss';

.container {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  .about {
    font-weight: 300;
    font-size: 23px;
    line-height: 27px;
    letter-spacing: 0.096em;
    margin-top: 1.5em;
    .row {
      margin-top: 1.5em;
    }
    p {
      &.internships {
        display: inline-block;
        width: 100%;
      }
      a {
        @include can-you-feel-the-love-tonight-text;
      }
    }
  }
}
.experience {
  text-align: left;
  ul {
    margin-left: 15px;
    li {
      list-style: none;
      position: relative;
      display: block;
      font-size: 20px;
      margin-top: 0.5em;
      letter-spacing: 0.195em;
      &::before {
        content: '';
        position: absolute;
        top: 1.4em;
        left: -4px;
        display: block;
        width: 19px;
        height: 2px;
        border-radius: 20px;
        background-color: #7e8496;
      }
    }
  }
}
img {
  width: 300px;
  position: absolute;
  top: 610px;
  right: -200px;
  transition: transform .4s ease;
}

@media(max-width: 767px) {
  .container {
    padding: 0 15 px;
    ul>li {
      letter-spacing: 0.1em;
    }
    .about {
      font-size: 20px;
    }
  }
}

@media(max-height: 780px) {
  .container {
    height: auto;
    margin-top: 80px;
  }
  .experience>ul>li {
      margin-top: 0.7em;
      line-height: 1.5em;
  }
}
</style>
