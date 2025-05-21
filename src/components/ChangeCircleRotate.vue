<template>
  <label>Circle Rotate</label>

  <br />

  <input
    type="number"
    @change="(event) => changeCircleAngle(event.target.value)"
  />
</template>

<script>
export default {
  props: ["changeCircleAngle"],
};
</script>
