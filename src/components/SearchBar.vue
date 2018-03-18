<template>
  <div id="SearchBar">
      <form>
        <div class="form-group container">
            <!--<label for="search">What are you looking for?</label>-->
            <input type="text" id="search" class="form-control" placeholder="What are you looking for?"/>
        </div>
        <button type="submit" class="btn btn-primary mb-2">Search</button>
      </form>
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
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
