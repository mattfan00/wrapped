<template>
  <div ref="main" class="main bg-black">
    <div v-if="section == 2" class="section-2-transition"></div>
    <div v-if="section == 3" class="section-3-transition"></div>

    <Intro @next-section="nextSection" v-if="section == 1" />
    <Timeline @next-section="nextSection" v-else-if="section == 2" />
    <Food @next-section="nextSection" v-else-if="section == 3" />

  </div>
</template>

<script>
import Intro from "./components/Intro"
import Timeline from "./components/Timeline"
import Food from "./components/Food"

export default {
  name: 'App',
  components: {
    Intro,
    Timeline,
    Food,
  },

  data() {
    return {
      section: 1,
    }
  },

  methods: {
    nextSection() {
      this.section++
      setTimeout(() => {
        console.log("hie")
        if (this.section == 2) {
          this.$refs.main.classList.replace("bg-black", "bg-orange")
        } else if (this.section == 3) {
          this.$refs.main.classList.replace("bg-orange", "bg-blue")
        }
      }, 2000)
    }
  }
}
</script>

<style lang="scss">

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

.section-2-transition {
  position: absolute;
  bottom: 0;
  height: 0;
  width: 100%;
  background-color: #f5ad06;
  animation: section-2-transition 2s;
  // animation-fill-mode: forwards;
  z-index: 0;
}

.section-3-transition {
  position: absolute;
  bottom: 0;
  height: 0;
  width: 100%;
  background-color: #3b01e2;
  animation: section-3-transition 2s;
  // animation-fill-mode: forwards;
  z-index: 0;
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
  16.66666666667% {
    opacity: 1;
    transform: translate(0, 0);
  }
  83.33333333334% {
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
