<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
};
</script>

<style>
body{
  background-image: linear-gradient(50deg ,#3498DB, #52BE80, #F39C12, #E74C3C);
  background-size: 400%;
  animation: fundo 15s infinite;
}
.fundo{
  position: relative;
  left: -50%;
  transform: translate(-50%, -50%);
}
@keyframes fundo{
  0%{
    background-position: 0 50%;
  }
  50%{
    background-position: 100% 50%;
  }
  100%{
    background-position: 0 50%;
  }
}
</style>