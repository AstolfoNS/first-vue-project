<template>
  <br />

  <slot />

  <select @change="(event) => $emit('change-text-color', event.target.value)">
    <option value="green">Green</option>
    <option value="red">Red</option>
    <option value="blue">Blue</option>
  </select>
</template>

<script>
export default {
  // props: ["changeTextColor"],
  emits: ["change-text-color"],
};
</script>
