<template>
  <div ref="container" class="section-6">
    <div class="center">
      <div class="first">
        <div class="big">So, if you</div>
        <div class="big">have known me</div>
        <div class="big">for this <span class="highlight">long</span></div>
      </div>
    </div>
    <div class="center">
      <div class="second">
        <div class="big">I'm sure you</div>
        <div class="big">can get all</div>
        <div class="big">of these <span class="highlight">right</span></div>
      </div>
    </div>
    <div class="center">
      <div class="third">
        <div class="big highlight">;)</div>
      </div>
    </div>

    <div class="quiz fourth">
      <div class="content">
        <div class="big title"><span class="highlight">Quiz</span> time!</div>
        <div class="middle">
          <div class="grid">
            <div class="question">
              <div class="medium highlight">
                What is my favorite ice cream flavor?
              </div>
              <div class="options">
                <button
                  :class="{
                    'incorrect': question1.selected != null && question1.selected == 0 && question1.selected != question1.answer,
                    'correct': question1.selected != null && question1.answer == 0,
                  }"
                  @click="question1Answer(0)"
                >Cookie dough</button>
                <button
                  :class="{
                    'incorrect': question1.selected != null && question1.selected == 1 && question1.selected != question1.answer,
                    'correct': question1.selected != null && question1.answer == 1,
                  }"
                  @click="question1Answer(1)"
                >Cookies and cream</button>
                <button
                  :class="{
                    'incorrect': question1.selected != null && question1.selected == 2 && question1.selected != question1.answer,
                    'correct': question1.selected != null && question1.answer == 2,
                  }"
                  @click="question1Answer(2)"
                >Mint chocolate chip</button>
                <button
                  :class="{
                    'incorrect': question1.selected != null && question1.selected == 3 && question1.selected != question1.answer,
                    'correct': question1.selected != null && question1.answer == 3,
                  }"
                  @click="question1Answer(3)"
                >Vanilla</button>
              </div>
            </div>
            <div class="question">
              <div class="medium highlight">
                What was my favorite date night?
              </div>
              <div class="options">
                <button
                  :class="{
                    'incorrect': question2.selected != null && question2.selected == 0 && question2.selected != question2.answer,
                    'correct': question2.selected != null && question2.answer == 0,
                  }"
                  @click="question2Answer(0)"
                >Madame Vo</button>
                <button
                  :class="{
                    'incorrect': question2.selected != null && question2.selected == 1 && question2.selected != question2.answer,
                    'correct': question2.selected != null && question2.answer == 1,
                  }"
                  @click="question2Answer(1)"
                >Chinese takeout and boba</button>
                <button
                  :class="{
                    'incorrect': question2.selected != null && question2.selected == 2 && question2.selected != question2.answer,
                    'correct': question2.selected != null && question2.answer == 2,
                  }"
                  @click="question2Answer(2)"
                >Cote</button>
                <button
                  :class="{
                    'incorrect': question2.selected != null && question2.selected == 3 && question2.selected != question2.answer,
                    'correct': question2.selected != null && question2.answer == 3,
                  }"
                  @click="question2Answer(3)"
                >Oishii Bowl and TV</button>
              </div>
            </div>
            <div class="question">
              <div class="medium highlight">
                What is my favorite song?
              </div>
              <div class="options">
                <button
                  :class="{
                    'incorrect': question3.selected != null && question3.selected == 0 && question3.selected != question3.answer,
                    'correct': question3.selected != null && question3.answer == 0,
                  }"
                  @click="question3Answer(0)"
                >New Light - John Mayer</button>
                <button
                  :class="{
                    'incorrect': question3.selected != null && question3.selected == 1 && question3.selected != question3.answer,
                    'correct': question3.selected != null && question3.answer == 1,
                  }"
                  @click="question3Answer(1)"
                >Stay - Kygo</button>
                <button
                  :class="{
                    'incorrect': question3.selected != null && question3.selected == 2 && question3.selected != question3.answer,
                    'correct': question3.selected != null && question3.answer == 2,
                  }"
                  @click="question3Answer(2)"
                >Toxic - Britney Spears</button>
                <button
                  :class="{
                    'incorrect': question3.selected != null && question3.selected == 3 && question3.selected != question3.answer,
                    'correct': question3.selected != null && question3.answer == 3,
                  }"
                  @click="question3Answer(3)"
                >I Feel It Coming - The Weeknd</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>


    <div class="arrows">
      <i class="right fas fa-arrow-right" @click="nextSection()"></i>
    </div>
  </div>
</template>

<script>

export default {
  name: "Quiz",

  data() {
    return {
      question1: {
        selected: null,
        answer: 1
      },
      question2: {
        selected: null,
        answer: 1
      },
      question3: {
        selected: null,
        answer: 3
      }
    }
  },

  methods: {
    nextSection() {
      this.$refs.container.classList.add("fade-out")
      setTimeout(() => {
        this.$emit("next-section")
        console.log("emit")
      }, 1000)
    },

    question1Answer(selected) {
      if (this.question1.selected == null) {
        console.log(selected)
        this.question1.selected = selected
      }
    },

    question2Answer(selected) {
      if (this.question2.selected == null) {
        console.log(selected)
        this.question2.selected = selected
      }
    },

    question3Answer(selected) {
      if (this.question3.selected == null) {
        console.log(selected)
        this.question3.selected = selected
      }
    },
  }
}
</script>

<style lang="scss" scoped>

.section-6 {
  position: absolute;
  height: 100vh;
  width: 100vw;
  color: black;
  z-index: 10;
}

.fade-out {
  animation: fade-out 1s;
  animation-fill-mode: forwards;
}

.highlight {
  color: #cb1582;
}

.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);

  .first {
    opacity: 0;
    animation: fade-in-out 4s;
    animation-delay: 2s;
  }
  .second {
    opacity: 0;
    animation: fade-in-out 4s;
    animation-delay: 6.5s;
  }
  .third{
    opacity: 0;
    animation: fade-in-out 4s;
    animation-delay: 11s;
  }
  .fourth {
    opacity: 0;
    animation: fade-in 1s;
    animation-delay: 15.5s;
  }
}

.fourth {
  opacity: 0;
  animation: fade-in 1s;
  animation-delay: 15.5s;
  animation-fill-mode: forwards;
}

.quiz {
  height: 100vh;
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;

  .content {
    width: 1000px;

    .title {
      opacity: 0;
      animation: fade-in 1s;
      animation-delay: 2s;
      animation-fill-mode: forwards;
    }

    .middle{
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-top: 40px;
    }

    .movie {
      .caption {
        margin-top: 10px;
      }
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      grid-gap: 40px;

      .question {
        background-color: #d4fff7;
        padding: 20px;
        border-radius: 12px;

        .options {
          margin-top: 30px;
          button {
            display: block;
            width: 100%;
            background-color: #d4f1eb;
            margin: 10px 0;
            border: none;
            border-radius: 5px;
            padding: 15px;
            cursor: pointer;
            transition: 0.5s;
            font-weight: bold;
          }

          // button:hover {
          //   background-color: #c1e9e0;
          // }

          button:focus {
            outline: none;
            box-shadow: none;
          }

          .incorrect {
            background-color: #e89595 !important;
          }

          .correct {
            background-color: #a9f3a9 !important;
          }
        }
      }
    }
  }

}


</style>