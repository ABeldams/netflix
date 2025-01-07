
<script>
import welcome from './components/welcome.vue'
import movies from './components/moviesCard.vue'
import more from './components/more.vue'
import Faq from './components/Faq.vue';
import contact from './components/contact.vue';
import foot from './components/footer.vue';
export default {
  name: 'App',
  components: {
    welcome,
    movies,
    more,
    Faq,
    contact,
    foot,
  },
};
</script>

<template>

<div id="app">

  
  <welcome/>
  <movies/>
  <more/>
  <Faq/>
  <contact/>
  <foot/>
   
  </div>
</template>

<style scoped>
</style>
