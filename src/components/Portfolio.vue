<template>
  <div class="container">
    <div class="row">
      <div class="col-md-3 timeline">
        <div class="row" v-for="item in timeline" :key="item.year">
          <span class="year">{{item.year}}</span>
          <div class="projects" v-for="project in item.projects" :key="project.name">
            <span>{{project.name}}</span>
            <ul class="tags list-inline">
              <li v-for="tag in project.tags" :key="tag">{{tag}}</li>
            </ul>
          </div>
        </div>
      </div>
      <div class="col-md project-info">

      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      timeline: [
        {
          year: 2012,
          projects: [{
            name: 'stalker online cheat',
            tags: ['C++', 'gamedev'],
            href: '#',
          }],
        },
        {
          year: 2013,
          projects: [{
            name: 'SZOHack launcher',
            tags: ['C#'],
            href: '#',
          }],
        },
        {
          year: 2014,
          projects: [{
            name: 'Terraria clone draft',
            tags: ['C#', 'Unity', 'gamedev'],
            href: '#',
          }],
        },
        {
          year: 2015,
          projects: [{
            name: 'SteamMultiAccount',
            tags: ['C#'],
            href: '#',
          }],
        },
      ],
    };
  },
  name: 'Portfolio',
};
</script>

<style lang="scss" scoped>
@import '../scss/mixins.scss';

.timeline {
  font-weight: 200;
  font-size: 23px;
  line-height: 1.2em;
  text-align: center;
  letter-spacing: 0.096em;
  .year {
    margin-bottom: 15px;
    &::after {
      content: '';
      display: block;
      @include can-you-feel-the-love-tonight;
      width: 60%;
      height: 3px;
      margin: auto;
      margin-top: 1px;
      border-radius: 3px;
    }
  }
  .projects {
    .tags {
      li {
        display: inline;
        font-size: 16px;
        background-color: #4568DC;
        border-radius: 40px;
        padding: 3px 8px;
        margin-right: 4px;
      }
    }
  }
}
</style>
