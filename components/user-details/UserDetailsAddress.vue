<template>
  <section class="md:border md:p-4">
    <h2 class="mb-2 text-xl font-semibold">Address</h2>
    <p>{{ address.suite }} {{ address.street }}, {{ address.city }}, {{ address.zipcode }}</p>
  </section>
</template>

<script>
export default {
  props: {
    user: {
      type: Object,
      required: true
    }
  },
  computed: {
    address() {
      return this.user.address;
    }
  }
};
</script>