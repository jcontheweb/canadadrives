<template>
  <div class="flex items-center justify-center">Redirecting to /users ...</div>
</template>

<script>
export default {
  head() {
    return {
      title: "Home"
    };
  },
  created() {
    this.$router.push("/users");
  }
};
</script>