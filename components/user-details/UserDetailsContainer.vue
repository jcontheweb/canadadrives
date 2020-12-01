<template>
  <p v-if="$fetchState.pending">Fetching user...</p>
  <p v-else-if="$fetchState.error">Oops! Something went wrong</p>
  <div v-else>
    <h1 class="text-3xl font-semibold flex">
      <nuxt-link class="text-blue-500 hover:text-blue-400" to="/users">Users</nuxt-link>
      <span class="mx-2">></span>
      <span>{{ user.name }}</span>
    </h1>

    <div class="md:grid grid-cols-3 gap-4 mt-6">
      <UserDetailsContact class="mt-10 md:mt-0" :user="user" />
      <UserDetailsAddress class="mt-10 md:mt-0" :user="user" />
      <UserDetailsCompany class="mt-10 md:mt-0" :user="user" />
    </div>
  </div>
</template>

<script>
export default {
  components: {
    UserDetailsContact: () => import("./UserDetailsContact"),
    UserDetailsAddress: () => import("./UserDetailsAddress"),
    UserDetailsCompany: () => import("./UserDetailsCompany")
  },
  props: {
    id: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      user: null
    };
  },
  async fetch() {
    const { data } = await this.$axios.get(`/users/${this.id}`);

    this.user = data;
    this.$emit("fetch", this.user);
  }
};
</script>