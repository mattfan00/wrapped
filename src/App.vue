<template>
  <div ref="main" class="main bg-black">
    <div v-if="section == 2" class="section-2-transition"></div>
    <div v-if="section == 3" class="section-3-transition"></div>

    <Intro @next-section="nextSection" v-if="section == 1" />
    <Timeline @next-section="nextSection" v-else-if="section == 2" />

  </div>
</template>

<script>
import Intro from "./components/Intro"
import Timeline from "./components/Timeline"

export default {
  name: 'App',
  components: {
    Intro,
    Timeline,
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
          this.$refs.main.classList.replace("bg-orange", "bg-green")
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

.bg-black {
  background-color: black;
}

.bg-orange {
  background-color: orange;
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
  background-color: orange;
  animation: section-2-transition 2s;
  // animation-fill-mode: forwards;
  z-index: 0;
}

.section-3-transition {
  position: absolute;
  bottom: 0;
  height: 0;
  width: 100%;
  background-color: green;
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

</style>
