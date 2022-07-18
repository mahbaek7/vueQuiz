<script setup>
import quizMain from "./components/quizMain.vue";
</script>

<template>
  <div class="content-app">
    <div class="content-quiz">
      <header class="quiz-header">
        <h1 style="color: whitesmoke">quiz</h1>
      </header>
      <quiz-main @whereHere="moveBetweenQuestion"></quiz-main>
      <footer class="quiz-footer">
        <div class="box-btn">
          <button>Skip</button>
          <button @click="i++">Next</button>
        </div>
      </footer>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      movement: null,
      i: 0,
    };
  },
  methods: {
    moveBetweenQuestion(move) {  
      console.log("i hate all");
      console.log(move);
      this.movement = move;
      console.log(this.movement);
    },
  },
};
</script>
<style></style>
