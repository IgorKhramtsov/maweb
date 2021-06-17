<template>
  <section class="container-fluid">
    <div class="container">
      <div class="row">
        <div class="col-md-3 timeline">
          <div class="row" v-for="item in timeline" :key="item.year">
            <span class="year">{{item.year}}</span>
            <div class="projects" v-for="project in item.projects" :key="project.name">
              <span v-on:click="setProject(project)" class="pointer">{{project.name}}</span>
              <ul class="tags list-inline">
                <li v-for="tag in project.tags" :key="tag">{{tag}}</li>
              </ul>
            </div>
          </div>
        </div>
        <div :class="'col-md project-info'/* + (selectedProject == null ? 'invisible' : '')*/">
          <div class="row frame-wrapper">
            <div ref="container" class="frame">
              <ReceiptRecognition/>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Vue from 'vue';
import StalkerOnlineCheat from './Articles/StalkerOnlineCheat.vue';
import SZOHackLauncher from './Articles/SZOHackLauncher.vue';
import StarboundClone from './Articles/StarboundClone.vue';
import SteamMultiAccount from './Articles/SteamMultiAccount.vue';
import TFAuthenticator from './Articles/TFAuthenticator.vue';
import ReceiptRecognition from './Articles/ReceiptRecognition.vue';

export default {
  name: 'Portfolio',
  components: { ReceiptRecognition },
  data() {
    return {
      selectedProject: null,
      projects: [{
        name: 'SZOHack',
        tags: ['C++', 'gamedev'],
        year: 2012,
        href: StalkerOnlineCheat,
      }, {
        name: 'SZOHack launcher',
        tags: ['C#'],
        year: 2013,
        href: SZOHackLauncher,
      }, {
        name: 'Starbound clone draft',
        tags: ['C#', 'Unity', 'gamedev'],
        year: 2014,
        href: StarboundClone,
      }, {
        name: 'SteamMultiAccount',
        tags: ['C#'],
        year: 2015,
        href: SteamMultiAccount,
      }, {
        name: 'Steam2FAuthenticator',
        tags: ['C#'],
        year: 2016,
        href: TFAuthenticator,
      }, {
        name: 'Receipt recognition algorithm',
        tags: ['C++', 'openCV'],
        year: 2018,
        href: ReceiptRecognition,
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
  methods: {
    setProject(project) {
      this.selectedProject = project;
      const ComponentClass = Vue.extend(project.href);
      const instance = new ComponentClass();
      instance.$mount();
      const node = this.$refs.container;
      if (node.hasChildNodes()) {
        node.replaceChild(instance.$el, node.firstChild);
      } else {
        node.appendChild(instance.$el);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import '../scss/vars.scss';

.container-fluid {
  padding: 80px 0;
}
section {
  margin-top: 80px;
  ::-webkit-scrollbar {
    background: transparent;
  }
}
.timeline {
  margin-top: 10px;
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
      position: relative;
      left: -1px;
      @include dark-ocean;
      width: 60%;
      height: 2px;
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
        background-color: $can-you-feel-the-love-tonight-start-darker;
        color: #cccccc;
        border-radius: 40px;
        padding: 0 6px 0 8px;
        margin-right: 4px;
        margin-bottom: 4px;
      }
    }
  }
}
.project-info {
  text-align: left;
  line-height: 1.2em;
  font-size: 22px;
  letter-spacing: 0.096em;
  font-weight: 200;
  .title {
    width: 100%;
    margin-bottom: 8px;
    .name {
      width: auto;
      padding-left: 16px;
    }
    .year {
      width: auto;
      position: absolute;
      right: 0;
    }
  }
  .frame-wrapper {
    height: 100%;
    padding: 0 10px;
    .frame {
      height: 100%;
      width: 100%;
    }
  }
}
.pointer {
  cursor: pointer;
}
</style>
