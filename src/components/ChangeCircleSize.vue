<template>
  <label>Circle size</label>

  <br />

  <input
    type="number"
    :value="size"
    @change="(event) => changeCircleSize(event.target.value)"
  />
</template>

<script>
export default {
  props: ["changeCircleSize", "size"],
};
</script>
