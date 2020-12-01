<template>
  <div>
    <div class="sm:flex items-end justify-between">
      <h1 class="text-2xl font-medium">Users</h1>
      <div class="sm:flex mt-2 sm:mt-0">
        <UserListSearch v-model="query" />
        <UserListFilter class="sm:ml-4 mt-2 sm:mt-0" v-model="filter" :filters="filters" />
      </div>
    </div>
    <p v-if="$fetchState.pending">Fetching users...</p>
    <p v-else-if="$fetchState.error">Oops! Something went wrong.</p>
    <div class="border-t sm:border mt-4 -mx-4 sm:mx-0" v-else>
      <div v-if="filteredList.length > 0">
        <UserListItem v-for="user in filteredList" :key="user.id" :user="user" />
      </div>
      <p class="p-4" v-else>
        No users found with the text
        <strong>{{ query }}</strong> in their
        <strong>{{ filter }}</strong>.
      </p>
    </div>
  </div>
</template>

<script>
import filters from "./filters";
export default {
  components: {
    UserListFilter: () => import("./UserListFilter"),
    UserListSearch: () => import("./UserListSearch"),
    UserListItem: () => import("./UserListItem")
  },
  data() {
    return {
      users: [],
      filter: filters[0],
      query: "",
      filters
    };
  },
  async fetch() {
    const { data } = await this.$axios.get("/users");

    this.users = data;
  },
  computed: {
    filteredList() {
      const { filter, query, users } = this;
      // if the query string is empty return all users
      if (!query || !filter) return users;

      return users.filter(user =>
        user[filter].toLowerCase().includes(query.toLowerCase())
      );
    }
  }
};
</script>