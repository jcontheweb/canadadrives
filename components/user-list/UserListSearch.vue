<template>
  <label class="block">
    <span class="block">Search</span>
    <input @input="$emit('input', $event.target.value)" class="form-input w-full" type="text" />
  </label>
</template>

<script>
export default {
  props: {
    value: {
      type: String,
      required: true
    }
  }
};
</script>