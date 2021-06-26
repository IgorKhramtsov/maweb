<template>
  <section class="container-fluid">
    <div class="container">
      <div class="row">
        <div class="col-md-3 timeline">
          <img
            src="../assets/planet_2.svg"
            alt="planet"
            :style="{ transform: `translate3d(0px, ${scroll}%, 0px)` }"
          >
          <div v-for="item in timeline" :key="item.year" class="row">
            <span :class="`year selectable-text ${item.year == selectedYear ? 'active' : ''}`">
              {{ item.year }}
            </span>
            <div v-for="project in item.projects" :key="project.name" class="projects">
              <span
                :class="`pointer selectable-text ${project == selectedProject ? 'active' : ''}`"
                @click="setProject(projects.indexOf(project))"
              >
                {{ project.name }}
              </span>
              <ul :class="`tags list-inline ${project == selectedProject ? 'active' : ''}`">
                <li v-for="tag in project.tags" :key="tag">
                  {{ tag }}
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div :class="'col-md project-info'/* + (selectedProject == null ? 'invisible' : '')*/">
          <div class="row frame-wrapper">
            <div ref="container" class="frame" />
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
import ECommerce from './Articles/ECommerce.vue';

export default {
  name: 'Portfolio',
  components: { },
  data() {
    return {
      selectedProjectIndex: 0,
      scroll: 0,
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
        tags: ['C#', 'unity', 'gamedev'],
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
        tags: ['vue', 'php', 'laravel'],
        year: 2018,
        href: ECommerce,
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
        tags: ['flutter', 'android', 'ios', 'grpc', 'firebase', 'sqlite', 'protobuf'],
        year: 'currently',
        href: '#',
      }],
    };
  },
  computed: {
    selectedProject() {
      return this.projects[this.selectedProjectIndex];
    },
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
    selectedYear() {
      if (this.selectedProject != null) {
        return this.selectedProject.year;
      }
      return null;
    },
  },
  mounted() {
    document.addEventListener('scroll', this.handleScroll);
    this.setProject(this.selectedProjectIndex);
  },
  unmounted() {
    document.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    setProject(index) {
      this.selectedProjectIndex = index;
      const ComponentClass = Vue.extend(this.selectedProject.href);
      const instance = new ComponentClass();
      instance.$mount();
      const node = this.$refs.container;
      if (node.hasChildNodes()) {
        node.replaceChild(instance.$el, node.firstChild);
      } else {
        node.appendChild(instance.$el);
      }
    },
    handleScroll() {
      const { scrollY } = window;
      const height = document.body.offsetHeight;
      this.scroll = ((height - scrollY) / (height * 1.0)) * 200;
    },
  },
};
</script>

<style lang="scss" scoped>
@import '../scss/vars.scss';
$text-trasparentize: .5;

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
  position: relative;
  img {
    position: absolute;
    left: -250px;
    bottom: 30%;
    width: 250px;
    transition: transform .4s ease;
  }
  .selectable-text {
    transition: color .15s ease;
    color: transparentize($color: $text-color, $amount: $text-trasparentize);
    &.active {
      color: $text-color;
    }
    &.pointer { // project name
      &:hover {
        color: $text-color;
      }
    }
  }
  .year {
    margin-bottom: 15px;
    &.active::after {
      @include dark-ocean;
    }
    &::after {
      content: '';
      display: block;
      position: relative;
      left: -1px;
      background-color: $disabled-item;
      width: 60%;
      height: 2px;
      margin: auto;
      margin-top: 1px;
      border-radius: 3px;
    }
  }
  .projects {
    .tags {
      &.active>li{
        background-color: $can-you-feel-the-love-tonight-start-darker;
        color: #cccccc;
      }
      li {
        transition: color background-color .15s ease;
        background-color: $disabled-item;
        color: transparentize(#cccccc, $text-trasparentize);
        display: inline-block;
        font-size: 16px;
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
