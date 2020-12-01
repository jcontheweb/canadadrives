<template>
  <div>
    <UserDetailsContainer @fetch="user = $event" :id="$route.params.id" />
    <UserPostsContainer :user="user" :id="$route.params.id" />
  </div>
</template>

<script>
export default {
  components: {
    UserDetailsContainer: () =>
      import("@/components/user-details/UserDetailsContainer"),
    UserPostsContainer: () =>
      import("@/components/user-posts/UserPostsContainer")
  },
  head() {
    return {
      title: this.user ? this.user.name : "..."
    };
  },
  data() {
    return {
      user: null
    };
  }
};
</script>
