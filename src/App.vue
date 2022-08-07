<script>
import quizMainVue from "./components/quizMainvue.vue";
export default {
  components: { quizMainVue },
  data() {
    return {
      moveNext: 0,
    };
  },
  methods: {
    NextQuestion() {
      if (this.moveNext < 3) {
        return this.moveNext++;
      }
    }, 
    correctchoice(correct){
      console.log("correct :"+ correct)
    }
  },
};
</script>

<template>
  <div class="content-app">
    <div class="content-quiz">
      <header class="quiz-header"><h1>quiz</h1></header>
      <quizMainVue :moveNext="moveNext" @correctchoice="correctchoice(correct)"></quizMainVue>
      <footer class="quiz-footer">
        <div class="box-btn">
          <button>Skip</button>
          <button @click="NextQuestion">Next</button>
        </div>
      </footer>
    </div>
  </div>
</template>

<style></style>
