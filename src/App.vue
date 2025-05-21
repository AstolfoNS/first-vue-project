<script>
import TogglePurple from "./components/TogglePurple.vue";
import ChoseTextColor from "./components/ChoseTextColor.vue";

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
  },
};
</script>

<template>
  <div class="container">
    <TogglePurple :togglePurple="togglePurple" />
    <br />

    <ChoseTextColor :changeTextColor="changeTextColor" />
    <br />

    <label>Circle size</label>
    <br />
    <input type="number" v-model="size" />
    <br />

    <label>Circle Rotate</label>
    <br />
    <input type="number" v-model="angle" />
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
