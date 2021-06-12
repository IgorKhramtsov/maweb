<template>
  <section class='container'>
    <div class="about">
      <div class="row">
        <p>started coding at 15, made a few personal projects,
          <br>and successfully get the Bachelor’s degree.
        </p>
      </div>
      <div class="row">
        <p class="internships">complete internship at
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
            <li>gamedev (also hacking them)</li>
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
  </section>
</template>

<script>
export default {
  name: 'About',
  props: {
    internships: Array,
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
        bottom: -2px;
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
</style>
