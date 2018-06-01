<template>
  <div>
    <h1>Child Component</h1>
    <span>{{ value }}</span>
    <input type="text" :value="value" @input="$emit('input', $event.target.value)">
    <!-- <input type="text" :value="value"> -->
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
