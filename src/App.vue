<template>
  <div id="app">

<h1>Would you rather.......</h1>

<would-you-rather 
v-for="question in questions"
v-bind:id="question.id"
v-bind:question="question.question"
v-bind:answer1="question.answer1"
v-bind:answer2="question.answer2"
v-on:answer-changed="answerChanged"></would-you-rather>



<h2>Which one would you pick? </h2>

<p v-for="choice in choices"> {{choice}}</p>

  </div>
  
</template>


<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
  data() {
    return {
      questions: [
        {
          id: 0,
          question: 'Would you rather live in a house shaped like a triangle shape or like a circle? ',
          answer1: 'Triangle house',
          answer2: 'Circle house',
          
        },
        {
          id: 1,
          question: 'Be a wizard or superman',
          answer1: 'Be a Wizard',
          answer2: 'be superman'
        },
        {
          id: 2,
          question: ' Have an elephant-sized cat or cat-sized elephant ',
          answer1: 'Have elephant-sized cat',
          answer2: 'Have cat-sized elephant'

        },
      ],
      choices: []

    }
  },
  methods: {

    // this is the fuction to display answer1 and answer2 that radio button being pushed
    answerChanged (id, choice) {
     this.choices[id] = choice
    }
  }
}
</script>

<style>

  body {
    background: blanchedalmond
  }
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background: gainsboro
}
</style>
