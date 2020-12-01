<template>
  <nuxt-link
    :to="`/users/${user.id}`"
    class="p-4 border-b hover:bg-gray-100 last:border-b-0 flex items-center justify-between"
  >
    <img
      class="bg-gray-300 h-12 w-12 sm:h-10 sm:w-10 rounded-full overflow-hidden"
      :src="`https://ui-avatars.com/api/?name=${user.name}`"
      alt
    />
    <div class="sm:flex flex-1 ml-4 justify-between items-center">
      <div>
        <p class="leading-none">{{ user.name }}</p>
        <p class="leading-none mt-1">{{ user.username }}</p>
      </div>
      <a
        @click.stop
        :href="`mailto:${user.email}`"
        class="text-blue-500 hover:text-blue-400 leading-none mt-1 sm:mt-0 block"
      >{{ user.email }}</a>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  props: {
    user: {
      type: Object,
      required: true
    }
  }
};
</script>