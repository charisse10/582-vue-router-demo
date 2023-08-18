<template>
  <nav>
    <div @click="this.$router.go(-1)">Go Back</div>
    <div @click="this.$router.go(1)">Go Forward</div>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/demo/1">After</router-link> |
    <div @click="this.$router.push({ name: 'prop', params: { id: 1 } })">
      Prop
    </div>
    <router-link to="/before/1">Before</router-link>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
};
</script>
