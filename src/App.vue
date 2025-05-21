<script>
import TogglePurple from "./components/TogglePurple.vue";

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
  },
};
</script>

<template>
  <div class="container">
    <TogglePurple :togglePurple="togglePurple" />

    <br />

    <label>Text color</label>
    <br />
    <select v-model="textColor">
      <option value="green">Green</option>
      <option value="red">Red</option>
      <option value="blue">Blue</option>
    </select>
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
