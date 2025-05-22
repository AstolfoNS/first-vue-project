<template>
  <div class="container">
    <TogglePurple @toggle-purple="togglePurple" />
    <br />

    <ChoseTextColor @change-text-color="changeTextColor" />
    <br />

    <ChangeCircleSize :changeCircleSize="changeCircleSize" :size="size" />
    <br />

    <ChangeCircleRotate :changeCircleAngle="changeCircleAngle" :angle="angle" />
    <br />

    <Circle
      :circleClass="circleClass"
      :circleSize="circleSize"
      :circleAngle="circleAngle"
      :textColor="textColor"
    />
    <br />
  </div>
</template>

<script>
import TogglePurple from "./components/TogglePurple.vue";
import ChoseTextColor from "./components/ChoseTextColor.vue";
import ChangeCircleSize from "./components/ChangeCircleSize.vue";
import ChangeCircleRotate from "./components/ChangeCircleRotate.vue";
import Circle from "./components/Circle.vue";

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
    Circle,
  },
};
</script>

<style scoped></style>
