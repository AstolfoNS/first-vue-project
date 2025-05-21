<template>
  <label><input type="checkbox" @change="togglePurple" />Purple</label>
</template>

<script>
export default {
  props: ["togglePurple"], // 接收父组件传递的函数
};
</script>
