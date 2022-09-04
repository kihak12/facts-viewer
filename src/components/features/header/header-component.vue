<template>
  <header>
    <img alt="Vue logo" src="../../../assets/logo.png" />
    <h2 class="header-title">Facts Viewer</h2>
  </header>
</template>

<script>
export default {
  name: "headerComponent",
  data() {
    return {};
  },
};
</script>

<style scoped>
header {
  height: 80px;
  background-color: #4158D0;
  background-image: linear-gradient(43deg, #caffe2 0%, #f08fe9d5 46%, #FFCC70 100%);
  display: flex;
  flex-direction: row;
  align-content: center;
  align-items: center;
  justify-content: space-between;
  overflow: hidden;
  padding: 0 1rem;
}

.header-title{
  font-size: 30px;
  color: #000;
}

img {
  height: 80%;
}
</style>