<template>
  <div class="color-bg">
    <fact-component></fact-component>
  </div>
</template>

<script>
import factComponentVue from '@/modules/components/facts-component/fact-component.vue';

export default {
  name: "app-component",
  components: {
    "fact-component": factComponentVue
  }
};
</script>

<style scoped>
  .color-bg{
    background-color: aliceblue;
  }
</style>