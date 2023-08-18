<template>
  <div class="demo">
    <demo-post />
    <h1>This is a demo page</h1>
    <p>{{ $route.params }}</p>
    <p>{{ users }}</p>
    <p>{{ user }}</p>
  </div>
</template>

<script>
import DemoPost from "../components/DemoPost.vue";
const users = [
  {
    id: 1,
    name: "John Doe",
  },
  {
    id: 2,
    name: "Jane Doe",
  },
  {
    id: 3,
    name: "Juan Dela Cruz",
  },
];
export default {
  name: "DemoView",
  components: {
    DemoPost,
  },
  data() {
    return {
      users,
      disabled: false,
    };
  },
  computed: {
    user() {
      for (let x of this.users) {
        if (x.id == this.$route.params.id) return x;
      }
      return { error: "User not found" };

      // return this.users.find((x) => x.id == this.$route.params.id);
    },
  },
};
</script>
