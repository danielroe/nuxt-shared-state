<template>
  <div>
    <p>{{ $route.name }}</p>

    <p>{{ $nuxt.context.route.name }}</p>

    <NuxtChild />
  </div>
</template>
<script>
export default {
  created() {
    if (process.server) {
      const { route, req } = this.$nuxt.context;
      const ctx1 = this.$nuxt.context;

      setTimeout(() => {
        console.log(
          "--------",
          this.$route.fullPath,
          this.$nuxt.context.route.fullPath,
          this.$nuxt.context == ctx1
        );
      }, 1000);
    }
  },
};
</script>
