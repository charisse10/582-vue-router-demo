<template>
  <NavBar />
  <router-view />
  <PropRouteView id="30000"></PropRouteView>
  <router-link to="/demo/1">Demo BEFORE</router-link>
</template>

<script>
import NavBar from "./components/NavBar.vue";
import PropRouteView from "./views/PropRouteView.vue";

export default {
  name: "App",
  components: {
    NavBar,
    PropRouteView,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

$vuegreen: #42b983;

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;
    text-decoration: none;

    &.router-link-exact-active {
      color: $vuegreen;
    }
  }

  .prop {
    font-weight: bold;
    color: #2c3e50;
    display: inline-block;

    &.prop:active {
      color: $vuegreen;
    }
  }

  div {
    &:active {
      color: $vuegreen;
    }
  }

  .prevnext {
    display: flex;
    justify-content: center;
    margin-bottom: 20px;
    font-weight: bold;
    color: #c0c0c0;
    cursor: pointer;

    .prev {
      margin-right: 15px;
    }

    .next {
      margin-left: 15px;
    }
  }
}
</style>
