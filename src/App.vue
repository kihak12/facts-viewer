<template>
  <div>
    <header-component></header-component>
    <app-component></app-component>
  </div>
</template>

<script>
import headerComponent from "./components/features/header/header-component.vue";
import appComponent from "./components/appComponent.vue";
export default {
  name: "App",
  components: {
    "app-component": appComponent,
    "header-component": headerComponent,
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@800&display=swap');

*,
:before,
:after {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
  font-family: 'Space Mono', monospace;
}
</style>