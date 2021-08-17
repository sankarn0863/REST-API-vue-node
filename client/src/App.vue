<template>
<div class="venu">
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/Work">Work</router-link>
    </div>
    <router-view />
  </div>
</div>
</template>
<style>
.venu{
    background-color: rgb(255, 255, 255);
}
</style>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

#nav {
  padding: 30px;

  a {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    color: #000000;
    text-decoration: none;
    font-size: 18px;

    &.router-link-exact-active {
      color: #0955c7;
    }
  }
}
</style>
