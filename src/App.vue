<template>
  <div>
    <pizzeria-home-page></pizzeria-home-page>
  </div>
</template>

<script>
import PizzeriaHomePage from './components/PizzeriaHomePage.vue';

export default {
  name: 'App',
  components: {
    PizzeriaHomePage
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
