<template>
  <div
    class="circle"
    :class="[circleClass, textColor]"
    :style="[circleSize, circleAngle]"
  >
    Hi
  </div>
</template>

<script>
export default {
  props: ["circleClass", "circleSize", "circleAngle", "textColor"],
};
</script>
