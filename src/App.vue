<template>
  <div id="app">
    <router-view name="header"/>
    <router-view/>
  </div>
</template>

<style lang="scss">
  @import './styles/index';

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    padding: 65px 0 0;
  }

</style>
