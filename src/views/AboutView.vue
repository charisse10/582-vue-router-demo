<template>
  <div class="about">
    <h1>This is an about page</h1>
    <h2>Demo with programatic routing</h2>

    <!-- <h3>With ID</h3>
    <div v-for="x in users" :key="x.id">
      <div :data-clickid="x.id" @click="handleCustomRouteId(x.id)">
        {{ x.name }}
      </div>
    </div> -->

    <h3>With Event</h3>
    <div v-for="x in users" :key="x.id">
      <div :data-clickid="x.id" @click="handleCustomRouteEvent">
        {{ x.name }}
      </div>
    </div>

    <h2>Demo with users list</h2>
    <div v-for="x in users" :key="x.id">
      <router-link :to="'/demo/' + x.id">User {{ x.id }}</router-link>
    </div>

    <!-- <h2>Demo with just numbers array</h2>
    <div v-for="x in [1, 2, 3, 4, 5, 6, 7]" :key="x">
      <router-link :to="'/demo/' + x">User {{ x }}</router-link>
    </div> -->
  </div>
</template>

<script>
export default {
  name: "AboutView",
  data() {
    return {
      users: [
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
      ],
    };
  },
  methods: {
    handleCustomRouteId(id) {
      this.$router.push("/demo/" + id);
    },
    handleCustomRouteEvent(event) {
      console.log(event.target);
      const id = event.target.dataset.clickid;
      // this.$router.push("/demo/" + id);
      for (let x of this.users) {
        if (x.id == id) {
          this.$router.push({ name: "demo", params: { id, name: x.name } });
          return;
        }
      }
    },
  },
};
</script>
