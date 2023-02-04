<template>
  <Home />
</template>

<script>
import HomePage from './components/HomePage.vue'

export default {
  name: 'App',
  components: {
    Home: HomePage
  }
}
</script>

<style>
@import './styles/reset.css';
@import './styles/index.css';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
}
</style>
