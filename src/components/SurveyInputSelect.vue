<template lang="pug">
  extends ./SurveyInputBase
  block input
    select(name="survey-select")
      //- each o,i in options
      //-   option(value=i) #{o}
      //- use v-for in favor of each syntax in pug
      //- https://naltatis.github.io/jade-syntax-docs/#for
      //- https://forums.meteor.com/t/loops-in-vue-with-jade-each-or-v-for/32916
      option(v-for="o, i in options" value=i) {{o}}
</template>

<script>
import SurveyInputBase from './SurveyInputBase';

export default {
  extends: SurveyInputBase,
  props: {
    options: {
      type: Array,
      default: function() {
        return [];
      }
    }
  }
};
</script>
