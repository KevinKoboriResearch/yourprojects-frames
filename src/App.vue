<template>
  <div id="q-app">
    <router-view />
  </div>
</template>
<script>
export default {
  name: 'App'
}
</script>

<style>
body::-webkit-scrollbar {
  width: 0px;
}

.q-card {
  border-radius: 0px;
}

.img-logo {
  height: 30px;
}

.img-bg {
  height: 100vh;
}

.footer-logo {
  height: 60px;
}

.rotate180 {
  transform: rotate(180deg);
}

.containerSizeTransition {
  transition: width .3s, height .3s;
}
</style>
