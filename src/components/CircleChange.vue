<template>
  <br />

  <slot />

  <input
    type="number"
    :value="param"
    @change="(event) => $emit('change-circle', event.target.value)"
  />
</template>

<script>
export default {
  props: ["param"],
  emits: ["change-circle"],
};
</script>
