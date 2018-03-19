<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <a href="https://github.com/abegomez/SearchApp" class="navbar-brand">
      <font-awesome-icon :icon="icon" size="lg" class="d-inline-block align-top" /> Tutorial Search</a>
    <button class="navbar-toggler" type="button" v-on:click="toggleMenu" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="true" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse order-3" id="navbarNavAltMarkup" v-bind:class="{ show: showMenu }">
      <div class="navbar-nav ml-auto">
        <a class="nav-item nav-link active" href="#">
          Home <span class="sr-only">(current)</span>
        </a>
        <a class="nav-item nav-link" href="https://github.com/abegomez">Github</a>
        <a class="nav-item nav-link" href="https://www.linkedin.com/in/abejg/">LinkedIn</a>
      </div>
    </div>
  </nav>
</template>

<script>
import FontAwesomeIcon from '@fortawesome/vue-fontawesome'
import { faChessPawn } from '@fortawesome/fontawesome-free-solid'

export default {
  name: 'navbar',
  data: () => ({
    showMenu: false
  }),
  computed: {
    icon () {
      return faChessPawn
    }
  },
  methods: {
    toggleMenu () {
      this.showMenu = !this.showMenu
    }
  },
  components: {
    FontAwesomeIcon
  }
}
</script>
