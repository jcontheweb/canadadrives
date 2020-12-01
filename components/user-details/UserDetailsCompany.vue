<template>
  <section class="md:border md:p-4">
    <h2 class="mb-2 text-xl font-semibold">Company</h2>
    <p>{{ company.name }}</p>
    <p>{{ company.bs }}</p>
    <p>{{ company.catchPhrase }}</p>
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
    company() {
      return this.user.company;
    }
  }
};
</script>