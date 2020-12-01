<template>
  <label class="block">
    <span class="block">Sort By</span>
    <select @input="$emit('input', $event.target.value)" class="form-select w-full">
      <option v-for="filter in filters" :key="filter" :value="filter">{{ filter }}</option>
    </select>
  </label>
</template>

<script>
export default {
  props: {
    filters: {
      type: Array,
      required: true
    }
  }
};
</script>