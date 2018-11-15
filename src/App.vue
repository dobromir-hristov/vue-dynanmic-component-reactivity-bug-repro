<template>
  <div id="app">
    <img width="25%" src="./assets/logo.png" />
    <component :is="currentComponent" /> <br />
    <button @click="prev">Prev</button> <button @click="next">Next</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    step: 1
  }),
  computed: {
    currentComponent() {
      const component = import(`@/components/Component${this.step}.vue`);
      return () => component;
    }
  },
  methods: {
    next() {
      this.step++;
    },
    prev() {
      this.step--;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
