<template>
  <div id="search-bar">
      <form>
        <div class="form-group container">
            <label for="search">What are you looking for?</label>
            <input type="text" v-model="search_term" id="search" class="form-control" placeholder="&#xF00e;"/>
        </div>
        <button type="submit" class="btn btn-primary mb-2">Search</button>
      </form>
  </div>
</template>

<script>
export default {
  name: 'search-bar',
  data () {
    return {}
  }
}
</script>

<style scoped>
    input {
        font-family: FontAwesome;
        font-style: normal;
        font-weight: normal;
        text-decoration: inherit;
    }
</style>
