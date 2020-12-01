<template>
  <section class="md:border md:p-4">
    <h2 class="mb-2 text-xl font-semibold">Contact Info</h2>
    <p>Username: {{ user.name }}</p>
    <p>
      Email:
      <a
        class="text-blue-500 hover:text-blue-400"
        :href="`mailto:${user.email}`"
      >{{ user.email }}</a>
    </p>
    <p>
      Phone:
      <a
        class="text-blue-500 hover:text-blue-400"
        :href="`tel:${user.phone}`"
      >{{ user.phone }}</a>
    </p>
    <p>
      Website:
      <a
        class="text-blue-500 hover:text-blue-400"
        :href="`http://${user.website}`"
        target="__blank"
      >{{ user.website }}</a>
    </p>
  </section>
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
