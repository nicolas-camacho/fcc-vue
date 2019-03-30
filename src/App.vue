<template>
  <div id="app">
    <Header
      :numberCorrectAnswers="numberCorrectAnswers"
      :numberQuestions="numberQuestions"
    />
    <b-container>
      <b-row>
        <b-col class="container">
          <img alt="Vue logo" src="./assets/logo.png">
        </b-col>
      </b-row>
      <b-row class="justify-content-md-center">
        <b-col sm="6">
          <QuestionBox
            v-if="questions.length" 
            :currentQuestion="questions[index]" 
            :next="next"
            :increment="increment"
          />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import QuestionBox from "./components/QuestionBox.vue";

export default {
  name: "app",
  components: {
    Header,
    QuestionBox
  },
  data() {
    return {
      questions: [],
      index: 0,
      numberCorrectAnswers: 0,
      numberQuestions: 0
    };
  },
  methods: {
    next() {
      this.index++
    },
    increment(isCorrect){
      if(isCorrect){
        this.numberCorrectAnswers++
      }

      this.numberQuestions++
    }
  },
  async mounted() {
    const response = await fetch("https://opentdb.com/api.php?amount=10&category=27&type=multiple")
    const jsonData = await response.json()
    this.questions = jsonData.results
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
