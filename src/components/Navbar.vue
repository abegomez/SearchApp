<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <router-link to="/" class="navbar-brand">
      <font-awesome-icon :icon="icon" /> Search App</router-link>
  </nav>
</template>

<script>
import FontAwesomeIcon from '@fortawesome/vue-fontawesome'
import { faChessPawn } from '@fortawesome/fontawesome-free-solid'

export default {
  name: 'navbar',
  computed: {
    icon () {
      return faChessPawn
    }
  },
  components: {
    FontAwesomeIcon
  }
}
</script>
