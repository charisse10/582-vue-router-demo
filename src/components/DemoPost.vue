<template>
  <div class="post">
    <h1>Demo AFTER Routing</h1>
    <div v-if="loading" class="loading">Loading...</div>

    <div v-if="error" class="error">{{ error }}</div>

    <div v-if="post" class="content">
      <h2>{{ post.title }}</h2>
      <p>{{ post.body }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      loading: false,
      post: null,
      error: null,
    };
  },
  created() {
    // watch the params of the route to fetch the data again
    this.$watch(
      () => this.$route.params,
      () => {
        this.fetchData();
      },
      // fetch the data when the view is created and the data is
      // already being observed
      { immediate: true }
    );
  },
  methods: {
    fetchData() {
      this.error = this.post = null;
      this.loading = true;
      // replace `getPost` with your data fetching util / API wrapper
      //   getPost(this.$route.params.id, (err, post) => {
      //     this.loading = false;
      //     if (err) {
      //       this.error = err.toString();
      //     } else {
      //       this.post = post;
      //     }
      //   });
      setTimeout(() => {
        this.loading = false;
        this.post = {
          title: "Demo Post",
          body: "This is a demo post",
        };
      }, 3000);
      // fetch(
      //   "https://jsonplaceholder.typicode.com/posts/" + this.$route.params.id
      // )
      //   .then((response) => response.json())
      //   .then((json) => {
      //     this.loading = false;
      //     this.post = json;
      //   })
      //   .catch((error) => {
      //     this.loading = false;
      //     this.error = error.toString();
      //   });
    },
  },
};
</script>
