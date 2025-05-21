<template>
  <label>Circle Rotate</label>

  <br />

  <input
    type="number"
    :value="angle"
    @change="(event) => changeCircleAngle(event.target.value)"
  />
</template>

<script>
export default {
  props: ["changeCircleAngle", "angle"],
};
</script>
