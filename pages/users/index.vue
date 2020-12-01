<template>
  <div>
    <UserListContainer />
  </div>
</template>

<script>
export default {
  components: {
    UserListContainer: () => import("@/components/user-list/UserListContainer")
  },
  head() {
    return {
      title: "Users"
    };
  }
};
</script>