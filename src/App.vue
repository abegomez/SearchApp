<template>
  <div id="app">
    <Navbar />
    <img src="./assets/logo.png">
    <router-view/>
  </div>
</template>

<script>
import Navbar from './components/Navbar'
import TutorialList from './components/TutorialList'
import { tutorials as tutorialData } from './data'

export default {
  name: 'App',
  components: { TutorialList },
  data: () => ({
    tutorials: []
  }),
  methods: {
    filterTutorials: function() {
    // TODO filtering
    this.tutorials = tutorialData
    }
  },
  created: function() {
    this.filterTutorials()
  },
  components: {
    Navbar
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
  margin-top: 10px;
}
</style>
