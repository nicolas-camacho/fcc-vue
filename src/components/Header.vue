<template>
  <div class="container">
    <b-nav tabs>
      <b-nav-item disabled>
        <h2>Quiz App</h2>
      </b-nav-item>
      <b-nav-item disabled><h2 class="counter">Counter: {{numberCorrectAnswers}}/{{numberQuestions}}</h2></b-nav-item>
    </b-nav>
  </div>
</template>

<script>
export default {
  props: [
    'numberCorrectAnswers',
    'numberQuestions'
  ]
}
</script>

<style scoped>
  h2{
    font-weight: bold !important;
    font-style: italic !important;
  }

  .counter{
    font-weight: lighter !important;
    font-style: normal !important;
  }
</style>

