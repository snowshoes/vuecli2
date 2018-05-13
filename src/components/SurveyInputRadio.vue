<template lang="pug">
  extends ./SurveyInputBase
  block input
    .labelradio(v-for="r, i in radios")
      input(type="radio", id=i, value=r)
      label(for=i) {{r}}
</template>

<script>
import SurveyInputBase from './SurveyInputBase';

export default {
  extends: SurveyInputBase,
  props: {
    radios: {
      type: Array,
      default() {
        return [];
      }
    }
  }
};
</script>
