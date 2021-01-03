<template>
  <div ref="main" class="main bg-black">
    <div v-if="section == 2" class="transition section-2-transition"></div>
    <div v-if="section == 3" class="transition section-3-transition"></div>
    <div v-if="section == 4" class="transition section-4-transition"></div>
    <div v-if="section == 5" class="transition section-5-transition"></div>
    <div v-if="section == 6" class="transition section-6-transition"></div>
    <div v-if="section == 7" class="transition section-2-transition"></div>
    <div v-if="section == 8" class="transition section-8-transition"></div>

    <Intro @next-section="nextSection" v-if="section == 1" />
    <Timeline @next-section="nextSection" v-else-if="section == 2" />
    <Food @next-section="nextSection" v-else-if="section == 3" />
    <Movies @next-section="nextSection" v-else-if="section == 4" />
    <Hours @next-section="nextSection" v-else-if="section == 5" />
    <Quiz @next-section="nextSection" v-else-if="section == 6" />
    <Monologue @next-section="nextSection" v-else-if="section == 7" />
    <Conclusion @next-section="nextSection" v-else-if="section == 8" />

  </div>
</template>

<script>
import Intro from "./components/Intro"
import Timeline from "./components/Timeline"
import Food from "./components/Food"
import Movies from "./components/Movies"
import Hours from "./components/Hours"
import Quiz from "./components/Quiz"
import Monologue from "./components/Monologue"
import Conclusion from "./components/Conclusion"

import {Howl} from 'howler';

export default {
  name: 'App',

  components: {
    Intro,
    Timeline,
    Food,
    Movies,
    Hours,
    Quiz,
    Monologue,
    Conclusion
  },

  data() {
    return {
      section: 1,
    }
  },

  methods: {
    nextSection() {
      if (this.section == 1) {
        this.playSong()
      }
      this.section++
      setTimeout(() => {
        if (this.section == 2) {
          this.$refs.main.classList.replace("bg-black", "bg-orange")
        } else if (this.section == 3) {
          this.$refs.main.classList.replace("bg-orange", "bg-blue")
        } else if (this.section == 4) {
          this.$refs.main.classList.replace("bg-blue", "bg-yellow")
        } else if (this.section == 5) {
          this.$refs.main.classList.replace("bg-yellow", "bg-pink")
        } else if (this.section == 6) {
          this.$refs.main.classList.replace("bg-pink", "bg-light-blue")
        } else if (this.section == 7) {
          this.$refs.main.classList.replace("bg-light-blue", "bg-orange")
        } else if (this.section == 8) {
          this.$refs.main.classList.replace("bg-orange", "bg-black")
        }
      }, 2000)
    },
    playSong() {
      console.log("howl")
      let love = new Howl({
        src: [require('./assets/love.mp3')],
        onend: () => {
          truly.play()
        }
      })

      let truly = new Howl({
        src: [require('./assets/truly.mp3')],
        onend: () => {
          trueBlue.play()
        }
      })

      let trueBlue = new Howl({
        src: [require('./assets/true.mp3')],
        onend: () => {
          love.play()
        }
      })


      love.play()
    }
  }
}
</script>

<style lang="scss">

button {
  position:absolute;
  z-index: 100;
}

body {
  margin: 0;
  overflow: hidden;
  font-family: 'Lato', sans-serif;
}

.main {
  position: relative;
  height: 100vh;
  width: 100vw;
}

.big {
  font-size: 4em;
  font-weight: bold;
}

.medium {
  font-size: 1.75em;
  font-weight: bold;
}

.small {
  margin-top: 30px;
  font-size: 1em;
}


.bg-black {
  background-color: black;
}

.bg-orange {
  background-color: #f5ad06;
}

.bg-blue {
  background-color: #3b01e2;
}

.bg-yellow {
  background-color: #cdf564;
}

.bg-pink {
  background-color: #cb1582;
}

.bg-light-blue {
  background-color: #a5ffee;
}

.arrows {
  position: absolute;
  bottom: 25px;
  right: 30px;

  i {
    font-size: 20px;
    color: white;
    cursor: pointer;
  }

  .left {
    margin-right: 10px;
  }

  .right {
    margin-left: 10px;
  }

}

.transition {
  position: absolute;
  bottom: 0;
  height: 0;
  width: 100%;
  z-index: 0;
}

.section-2-transition {
  background-color: #f5ad06;
  animation: section-2-transition 2s;
  // animation-fill-mode: forwards;
}

.section-3-transition {
  background-color: #3b01e2;
  animation: section-3-transition 2s;
  // animation-fill-mode: forwards;
}

.section-4-transition {
  background-color: #cdf564;
  animation: section-4-transition 2s;
  // animation-fill-mode: forwards;
}

.section-5-transition {
  background-color: #cb1582;
  animation: section-5-transition 2s;
  // animation-fill-mode: forwards;
}

.section-6-transition {
  background-color: #a5ffee;
  animation: section-6-transition 2s;
  // animation-fill-mode: forwards;
}

.section-8-transition {
  background-color: black;
  animation: section-8-transition 2s;
  // animation-fill-mode: forwards;
}

@keyframes section-2-transition {
  0% {
    height: 0;
  }
  100% {
    height: 100vh;
  }
}

@keyframes section-3-transition {
  0% {
    height: 0;
  }
  100% {
    height: 100vh;
  }
}

@keyframes section-4-transition {
  0% {
    height: 0;
  }
  100% {
    height: 100vh;
  }
}

@keyframes section-5-transition {
  0% {
    height: 0;
  }
  100% {
    height: 100vh;
  }
}

@keyframes section-6-transition {
  0% {
    height: 0;
  }
  100% {
    height: 100vh;
  }
}

@keyframes section-8-transition {
  0% {
    height: 0;
  }
  100% {
    height: 100vh;
  }
}

@keyframes fade-in-out {
  0% {
    opacity: 0;
    transform: translate(0, 30px);
  }
  25% {
    opacity: 1;
    transform: translate(0, 0);
  }
  75% {
    opacity: 1;
    transform: translate(0, 0);
  }
  100% {
    opacity: 0;
    transform: translate(0, 30px);
  }
}

@keyframes fade-in-out-long {
  0% {
    opacity: 0;
    transform: translate(0, 30px);
  }
  12.5% {
    opacity: 1;
    transform: translate(0, 0);
  }
  87.5% {
    opacity: 1;
    transform: translate(0, 0);
  }
  100% {
    opacity: 0;
    transform: translate(0, 30px);
  }
}

@keyframes fade-in-out-xlong {
  0% {
    opacity: 0;
    transform: translate(0, 30px);
  }
  5% {
    opacity: 1;
    transform: translate(0, 0);
  }
  95% {
    opacity: 1;
    transform: translate(0, 0);
  }
  100% {
    opacity: 0;
    transform: translate(0, 30px);
  }
}

@keyframes fade-in {
  0% {
    opacity: 0;
    transform: translate(0, 30px);
  }
  100% {
    opacity: 1;
    transform: translate(0, 0);
  }
}

@keyframes fade-out {
  0% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}
</style>
