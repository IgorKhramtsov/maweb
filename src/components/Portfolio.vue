<template>
  <div class="container">
    <div class="row">
      <div class="col-md-3 timeline">
        <div class="row" v-for="item in timeline" :key="item.year">
          <span class="year">{{item.year}}</span>
          <div class="projects" v-for="project in item.projects" :key="project.name">
            <span v-on:click="setProject(project)">{{project.name}}</span>
            <ul class="tags list-inline">
              <li v-for="tag in project.tags" :key="tag">{{tag}}</li>
            </ul>
          </div>
        </div>
      </div>
      <div class="col-md project-info" v-if="selectedProject != null">
        <span class="name">{{selectedProject.name}}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedProject: null,
      projects: [{
        name: 'stalker online cheat',
        tags: ['C++', 'gamedev'],
        year: 2012,
        href: '#',
      }, {
        name: 'SZOHack launcher',
        tags: ['C#'],
        year: 2013,
        href: '#',
      }, {
        name: 'Terraria clone draft',
        tags: ['C#', 'Unity', 'gamedev'],
        year: 2014,
        href: '#',
      }, {
        name: 'SteamMultiAccount',
        tags: ['C#'],
        year: 2015,
        href: '#',
      }, {
        name: 'Steam2FAuthenticator',
        tags: ['C#'],
        year: 2016,
        href: '#',
      }, {
        name: 'Minecraft Twitch integration mod',
        tags: ['Java', 'gamedev'],
        year: 2017,
        href: '#',
      }, {
        name: 'Receipt recognition',
        tags: ['C++', 'openCV'],
        year: 2018,
        href: '#',
      }, {
        name: 'Simple e-commerce website',
        tags: ['vue', 'php'],
        year: 2018,
        href: '#',
      }, {
        name: 'Compiler',
        tags: ['C++'],
        year: 2019,
        href: '#',
      }, {
        name: 'Beholder library',
        tags: ['C#', 'Java', 'gamedev'],
        year: 2019,
        href: '#',
      }, {
        name: 'DeEsser',
        tags: ['C++'],
        year: 2020,
        href: '#',
      }, {
        name: 'PhysMin',
        tags: ['typescript', 'react', 'firebase', 'android', 'kotlin'],
        year: 2020,
        href: '#',
      }, {
        name: 'Arkanoid',
        tags: ['C++', 'gamedev', 'opengl'],
        year: 2020,
        href: '#',
      }, {
        name: 'SingularityApp',
        tags: ['flutter'],
        year: 'currently',
        href: '#',
      }],
    };
  },
  methods: {
    setProject(project) {
      this.selectedProject = project;
    },
  },
  computed: {
    timeline() {
      const projectsByYear = {};
      const timeline = [];
      for (let i = 0; i < this.projects.length; i += 1) {
        if (projectsByYear[this.projects[i].year] == null) {
          projectsByYear[this.projects[i].year] = [];
        }
        projectsByYear[this.projects[i].year].push(this.projects[i]);
      }
      Object.keys(projectsByYear).forEach((key) => {
        timeline.push({
          year: key,
          projects: projectsByYear[key],
        });
      });

      return timeline;
    },
  },
  name: 'Portfolio',
};
</script>

<style lang="scss" scoped>
@import '../scss/mixins.scss';

.timeline {
  margin-top: 80px;
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
        display: inline-block;
        font-size: 16px;
        background-color: #4568DC;
        border-radius: 40px;
        padding: 0 6px 0 8px;
        margin-right: 4px;
        margin-bottom: 4px;
      }
    }
  }
}
.project-info {
  background: linear-gradient(108.88deg, rgba(1, 1, 1, 0.41) -6.23%, rgba(0, 0, 0, 0.041) 106.16%);
  border: 2px solid rgba(46, 41, 63, 0.56);
  border-radius: 26px;
  backdrop-filter: blur(150px);
  height: 60vh;
  text-align: left;
  padding: 8px;
  .name {
    line-height: 1.2em;
    font-size: 22px;
    padding-left: 12px;
    letter-spacing: 0.096em;
    font-weight: 200;
  }
}
</style>
