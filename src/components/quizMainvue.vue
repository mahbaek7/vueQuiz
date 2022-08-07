<template>
  <div>
    <section
      class="quiz-main"
      v-for="(query, id) in questions"
      :key="query.id"
      v-show="move === id"
      ref="ask"
    >
      <div>
        <h3 class="box-question">
          {{ query.question }}
        </h3>
        <div class="box-suggestions">
          <ul>
            <li
              v-for="(answer, index) in query.seggestions"
              :key="answer"
              @click="checkAnswer(index)"
            >
              {{ answer.suggestion }}
            </li>
          </ul>
        </div>
      </div>
      <div class="box_score"></div>
    </section>
  </div>
</template>
<script>
export default {
  data() {
    return {
      move: 0,
      questions: [
        {
          question: "inside which HTML element do we put ja",
          seggestions: [
            { suggestion: "<js>" },
            { suggestion: "<script>" },
            { suggestion: "<javascript>" },
            { suggestion: "<scripting>" },
          ],
          correct_Suggestion: "<script>",
        },
        {
          question: "where is the correct place to insert a ja",
          seggestions: [
            { suggestion: " the <body> section" },
            {
              suggestion:
                " both the <head> section and the<body> section are correct",
            },
            { suggestion: "<head> section" },
          ],
          correct_Suggestion:
            " both the <head> section and the<body> section are correct",
        },
        {
          question:
            "what the correct syntax for referring to an external script call xxx.js",
          seggestions: [
            { suggestion: "name= 'xxx.js'" },
            { suggestion: "herf='xxx.js'" },
            { suggestion: "src='xxx.js'" },
          ],
          correct_Suggestion: "src='xxx.js'",
        },
        {
          question: "the external javascrpt file must contain the <script> tag",
          seggestions: [{ suggestion: "false" }, { suggestion: "true" }],
          correct_Suggestion: "false",
        },
      ],
    };
  },
  methods: {
    checkAnswer() {
      // console.log(this.questions.seggestions.suggestion[index])
    },
    sendEmit() {
      this.$emit("whereHere", "mix my boy");
    },
  },
};
</script>