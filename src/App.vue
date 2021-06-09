<template>
  <div id="nav">
    <router-link :to="{name: Home}">Home</router-link>
  </div>
  <router-view/>
</template>

<style lang='scss'>
* {
  margin: auto;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: $white;
  background-color: $main;
}
</style>
