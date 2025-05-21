<template>
  <label>Text color</label>

  <br />

  <select @change="(event) => changeTextColor(event.target.value)">
    <option value="green">Green</option>
    <option value="red">Red</option>
    <option value="blue">Blue</option>
  </select>
</template>

<script>
export default {
  props: ["changeTextColor"],
};
</script>
