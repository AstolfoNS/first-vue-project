<script>
export default {
  data() {
    return {
      isPurple: false,
      textColor: "",
      size: 200,
      angle: 0,
    };
  },

  methods: {},
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
};
</script>

<template>
  <div class="container">
    <label><input type="checkbox" v-model="isPurple" />Purple</label>
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

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  height: 100vh;
  background-color: #f0f0f0;
}

.circle {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  width: 200px;
  height: 200px;
  border-radius: 50%;

  background-color: rgb(000, 000, 255);

  color: white;
}

.purple {
  background-color: rgb(128, 000, 128);
}

.blue {
  color: rgb(000, 000, 255);
}

.green {
  color: rgb(000, 255, 000);
}

.red {
  color: rgb(255, 000, 000);
}
</style>
