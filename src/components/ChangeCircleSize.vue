<template>
  <label>Circle size</label>

  <br />

  <input
    type="number"
    @change="(event) => changeCircleSize(event.target.value)"
  />
</template>

<script>
export default {
  props: ["changeCircleSize"],
};
</script>
