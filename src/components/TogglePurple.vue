<template>
  <br />

  <label>
    <input type="checkbox" @change="$emit('toggle-purple')" />

    <slot />
  </label>
</template>

<script>
export default {
  // props: ["togglePurple"],
  emits: ["toggle-purple"],
};
</script>
