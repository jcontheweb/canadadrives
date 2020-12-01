<template>
  <div>
    <UserListContainer />
  </div>
</template>

<script>
export default {
    components: {
        UserListContainer: () => import('@/components/user-list/UserListContainer')
    }
};
</script>