<template>
  <div id="app">
    <Header/>
    <b-container>
      <b-row>
        <b-col class="container">
          <img alt="Vue logo" src="./assets/logo.png">
        </b-col>
      </b-row>
      <b-row class="justify-content-md-center">
        <b-col sm="6">
          <QuestionBox/>
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
