<template>
  <div class="tutorial-list" :key="tutorials">
    <Tutorial class="tutorial" v-for="tutorial in tutorials" :item="tutorial" :key="tutorial" />
  </div>
</template>

<script>
import Tutorial from './Tutorial'

export default {
  name: 'tutorial-list',
  components: { Tutorial },
  props: ['tutorials']
}
</script>

<style scoped>
   .tutorial-list {
     margin: 20px 0;
     display: flex;
     justify-content: space-between;
     flex-flow: wrap;
   }

   .tutorial {
     padding: 20px;
   }

   @media only screen and (min-width: 600px) {
     .tutorial {
       width: 50%;
     }
   }
</style>
