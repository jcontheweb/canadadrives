<template>
  <div class="md:border md:p-4 border-b last:border-b-0 md:last:border-b py-4">
      <h2 v-html="post.title" class="font-semibold text-xl mb-2"></h2>
      <p v-html="post.body" class="leading-5"></p>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true
    }
  }
};
</script>