<template>
  <p v-if="$fetchState.pending">Fetching user posts</p>
  <p v-else-if="$fetchState.error">Oops! Something went wrong.</p>
  <div class="pt-8 md:pt-0 mt-8 md:mt-12 border-t md:border-t-0" v-else>
    <h2 v-if="user.name" class="text-3xl font-semibold">Posts by {{ user.name }}</h2>
    <h2 v-else class="text-3xl font-semibold">Posts by ...</h2>

    <div class="md:grid grid-cols-3 gap-4 mt-6">
        <UserPostItem v-for="post in posts" :key="post.id" :post="post" />
    </div>
  </div>
</template>

<script>
export default {
  components: {
    UserPostItem: () => import("./UserPostItem")
  },
  props: {
    id: {
      type: String,
      required: true
    },
    user: {
      type: Object,
      required: false
    }
  },
  data() {
    return {
      posts: null
    };
  },
  async fetch() {
    const { data } = await this.$axios.get(`/posts?userId=${this.id}`);

    this.posts = data;
  }
};
</script>