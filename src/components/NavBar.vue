<template>
  <nav>
    <div class="prevnext">
      <div class="prevt" @click="this.$router.go(-1)">PREV</div>
      <div class="next" @click="this.$router.go(1)">NEXT</div>
    </div>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/demo/1">After</router-link> |
    <router-link to="/before/1">Before</router-link> |
    <div
      class="prop"
      @click="this.$router.push({ name: 'prop', params: { id: 1 } })"
    >
      Prop
    </div>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
};
</script>
