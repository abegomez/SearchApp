<template>
  <div id="SearchBar">
      <form>
        <div class="form-group container">
            <!--<label for="search">What are you looking for?</label>-->
            <input type="search" :name="name" v-model="searchTerm" class="form-control" placeholder="What do you want to learn?"/>
        </div>
      </form>
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  data () {
    return { searchTerm: this.value }
  },
  watch: {
    value: function (val) {
      this.searchTerm = val
    },
    searchTerm: function (val) {
      this.$emit('input', val)
    }
  },
  props: {
    value: {
      default: ''
    },
    name: {
      default: ''
    }
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
