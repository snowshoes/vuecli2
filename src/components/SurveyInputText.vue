<template lang="pug">
  extends ./SurveyInputBase
  block input
   input(type="text", :placeholder="placeholder")
</template>

<script>
import SurveyInputBase from './SurveyInputBase';
export default {
  extends: SurveyInputBase,
  props: {
    placeholder: {
      type: String,
      default: 'e.g.'
    }
  }
};
</script>
