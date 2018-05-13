<template lang="pug">
  include SurveyInputBase
</template>

<script>
export default {
  props: {
    question: {
      type: String,
      default: ''
    }
  }
};
</script>
