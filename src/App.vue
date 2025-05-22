<template>
  <div class="container">
    <TogglePurple @toggle-purple="togglePurple" />
    <br />

    <ChoseTextColor @change-text-color="changeTextColor" />
    <br />

    <CircleChange @change-circle="changeCircleSize" :param="size">
      Circle size
    </CircleChange>

    <CircleChange @change-circle="changeCircleAngle" :param="angle">
      Circle rotate
    </CircleChange>

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
import CircleChange from "./components/CircleChange.vue";
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
    Circle,
    CircleChange,
  },
};
</script>

<style scoped></style>
