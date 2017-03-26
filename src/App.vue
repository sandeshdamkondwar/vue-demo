<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 10px;
  margin-top: 60px;
}

#loader {
  width: 50px;
  height: 50px;
  -webkit-animation: spin 2s linear infinite;
  animation: spin 2s linear infinite;
  -webkit-animation-timing-function: cubic-bezier(0.55, 0.15, 0.45, 0.85);
  animation-timing-function: cubic-bezier(0.55, 0.15, 0.45, 0.85);
}

@-webkit-keyframes spin {
  to {
    -webkit-transform: rotate(1turn)
  }
}

@keyframes spin {
  to {
    -webkit-transform: rotate(1turn);
    transform: rotate(1turn)
  }
}
</style>
