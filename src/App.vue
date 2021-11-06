<template>
  <TitleMovie msg='Movies' />
  <CardMovie />
</template>

<script>
import TitleMovie from './components/TitleMovie.vue'
import CardMovie from './pages/Home.vue'

export default {
  name: 'App',
  components: {
    TitleMovie,
    CardMovie    
  }
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
  background: #f0f0f0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0 auto;
  background: #f0f0f0;
  max-width: 1024px;
}
</style>
