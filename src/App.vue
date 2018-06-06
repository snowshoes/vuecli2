<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!-- <HelloWorld/> -->
    <survey-input-text :question="questionTest" :placeholder="placeholder" />
    <survey-input-select :question="questionSelect" :options="options"></survey-input-select>
    <survey-input-radio :question="questionReadio" :radios="radios"></survey-input-radio>
    <!-- <custom-input v-model="searchText"></custom-input> 的具体实现-->
    <!-- <custom-input :value="searchText" @input="searchText = arguments[0]"></custom-input> -->
    <custom-input :value="searchText" @input="searchText = $event"></custom-input>
    <br/>
    <custom-select />
    <br/>
    <survey-input-text :question="questionTest" :placeholder="placeholder" />
    <survey-input-select :question="questionSelect" :options="options"></survey-input-select>
    <custom-select />
    <survey-input-radio :question="questionReadio" :radios="radios"></survey-input-radio>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld';
import SurveyInputText from './components/SurveyInputText';
import SurveyInputSelect from './components/SurveyInputSelect';
import SurveyInputRadio from './components/SurveyInputRadio';
import CustomInput from './components/CustomInput';
import CustomSelect from './components/select/Select';

export default {
  name: 'App',
  components: {
    CustomInput,
    CustomSelect,
    SurveyInputText,
    SurveyInputSelect,
    SurveyInputRadio
  },
  // props: {
  //   value: {
  //     type: String,
  //     default: ''
  //   }
  // },
  data: function() {
    return {
      questionTest: '1. Do you use Vue.js ?',
      questionSelect: '2. Which UI Framework ?',
      questionReadio: '3. Which backend is better ?',
      placeholder: 'e.g. John Smith',
      options: ['Vue', 'Reactjs', 'Angular'],
      radios: ['Nodejs', 'J2EE', 'Golang'],
      searchText: 'Parent Value'
    };
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
