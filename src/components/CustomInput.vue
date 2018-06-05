<!-- This component shows how v-model interprete in vue -->
<!-- 结合有道云上的笔记看v-model原理 -->
<template>
  <div>
    <h1>Child Component</h1>
    <span>{{ value }}</span>
    <input type="text" :value="value" @input="$emit('input', $event.target.value)">
  </div>
</template>

<script>
export default {
  props: {
    value: {
      type: String,
      default: ''
    }
  },
  data() {
    return {};
  }
};
</script>
