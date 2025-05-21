<script>
import TogglePurple from "./components/TogglePurple.vue";
import ChoseTextColor from "./components/ChoseTextColor.vue";
import ChangeCircleSize from "./components/ChangeCircleSize.vue";
import ChangeCircleRotate from "./components/ChangeCircleRotate.vue";

export default {
  data() {
    return {
      isPurple: false,
      textColor: "",
      size: 200,
      angle: 0,
    };
  },

  methods: {
    togglePurple() {
      this.isPurple = !this.isPurple;
    },
    changeTextColor(color) {
      this.textColor = color;
    },
    changeCircleSize(size) {
      this.size = parseInt(size);
    },
    changeCircleAngle(angle) {
      this.angle = parseInt(angle);
    },
  },

  computed: {
    circleClass() {
      return {
        purple: this.isPurple,
      };
    },
    circleSize() {
      return {
        height: `${this.size}px`,
        width: `${this.size}px`,
        lineheight: `${this.size}px`,
      };
    },
    circleAngle() {
      return {
        transform: `rotate(${this.angle}deg)`,
      };
    },
  },

  components: {
    TogglePurple,
    ChoseTextColor,
    ChangeCircleSize,
    ChangeCircleRotate,
  },
};
</script>

<template>
  <div class="container">
    <TogglePurple :togglePurple="togglePurple" />
    <br />

    <ChoseTextColor :changeTextColor="changeTextColor" />
    <br />

    <ChangeCircleSize :changeCircleSize="changeCircleSize" :size="size" />
    <br />

    <ChangeCircleRotate :changeCircleAngle="changeCircleAngle" :angle="angle" />
    <br />

    <div
      class="circle"
      :class="[circleClass, textColor]"
      :style="[circleSize, circleAngle]"
    >
      Hi
    </div>
  </div>
</template>

<style scoped></style>
