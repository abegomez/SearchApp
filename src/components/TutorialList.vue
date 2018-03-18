<script>
  import TutorialList from './TutorialList'
  import Tutorial from './Tutorial'

  export default {
    name: 'tutorial-list',
    components: { Tutorial },
    props ['tutorials']
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
