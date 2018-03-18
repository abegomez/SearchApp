<template>
  <div id="app">
    <Navbar />
    <img src="./assets/logo.png">
      <SearchBar v-model="searchTerm" />
    <TutorialList :tutorials="pageOfTutorials" />
  </div>
</template>

<script>
import Navbar from './components/Navbar'
import TutorialList from './components/TutorialList'
import { tutorials as tutorialData } from './data'
import SearchBar from './components/SearchBar'

export default {
  name: 'App',
  components: {
    TutorialList,
    Navbar,
    SearchBar
  },
  data: () => ({
    tutorials: [],
    searchTerm: '',
    page: 1
  }),
  watch: {
    searchTerm: function () {
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
      let result = tutorialData

      if (searchTerm) {
        result = result.filter(tutorial => {
          return (
            tutorial.title.toLowerCase().search(searchTerm) >= 0 ||
            tutorial.description.toLowerCase().search(searchTerm) >= 0
          )
        })
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
</style>
