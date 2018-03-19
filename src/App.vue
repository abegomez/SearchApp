<template>
  <div id="app">
    <Navbar />
    <img src="./assets/logo.png" />
    <SearchBar v-model="searchTerm" />
    <Keywords v-model="tech" />
    <TutorialList :tutorials="pageOfTutorials" />
  </div>
</template>

<script>
import Navbar from './components/Navbar'
import TutorialList from './components/TutorialList'
import { tutorials as tutorialData } from './data'
import SearchBar from './components/SearchBar'
import Keywords from './components/Keywords'

export default {
  name: 'App',
  components: {
    TutorialList,
    Navbar,
    SearchBar,
    Keywords
  },
  data: () => ({
    tutorials: [],
    searchTerm: '',
    tech: '',
    page: 1
  }),
  watch: {
    searchTerm: function () {
      this.filterTutorials()
    },
    tech: function () {
      this.filterTutorials()
    }
  },
  computed: {
    pageOfTutorials: function () {
      return this.tutorials
    }
  },
  methods: {
    filterTutorials: function () {
      const searchTerm = this.searchTerm.toLowerCase()
      const tech = this.tech
      let result = tutorialData

      if (searchTerm) {
        result = result.filter(tutorial => {
          return (
            tutorial.title.toLowerCase().search(searchTerm) >= 0 ||
            tutorial.description.toLowerCase().search(searchTerm) >= 0
          )
        })
      }
      // Keyword filter
      if (tech) {
        result = result.filter(tutorial => tutorial.tech.indexOf(tech) >= 0)
      }

      this.tutorials = result
      this.page = 1
    }
  },
  created: function () {
    this.filterTutorials()
  }
}
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }

  img {
    transform-origin:50% 50%;
    animation:2s rotateRight linear;
    animation-fill-mode: forwards;
  }

  @keyframes rotateRight {
    100%{ transform:rotate(180deg); }
  }
</style>
