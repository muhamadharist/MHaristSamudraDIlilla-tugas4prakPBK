<template>
  <div id="app">
    <brand-component></brand-component>
  </div>
</template>

<script>
import BrandComponent from './components/BrandComponent.vue';

export default {
  name: 'App',
  components: {
    BrandComponent,
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
