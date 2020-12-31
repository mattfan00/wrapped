<template>
  <div ref="container" class="section-7">
    <div class="center">
      <div class="one">
        <div class="big">Despite the</div>
        <div class="big"><span class="highlight">score</span> you got,</div>
      </div>
    </div>
    <div class="center">
      <div class="two">
        <div class="big">Our relationship is</div>
        <div class="big"><span class="highlight">defined</span> by...</div>
      </div>
    </div>
    <div class="three">
      <div class="medium">Facetime calls</div>
      <div class="medium">in weird places</div>
    </div>
    <div class="four">
      <div class="medium">Gold digger</div>
      <div class="medium">hearts</div>
    </div>
    <div class="five">
      <div class="medium">Facemask selfies</div>
    </div>
    <div class="six">
      <div class="medium">Food excursions</div>
    </div>
    <div class="seven">
      <div class="medium">(Mostly Asian food)</div>
    </div>
    <div class="eight">
      <div class="medium">Chinese Sausage</div>
      <div class="medium">and Da Tastie</div>
    </div>
    <div class="nine">
      <div class="medium">Worth It videos</div>
    </div>
    <div class="ten">
      <div class="medium">That's what</div>
      <div class="medium">she said</div>
    </div>
    <div class="eleven">
      <div class="medium">Doing nothing</div>
    </div>
    <div class="twelve">
      <div class="medium">Laying on top</div>
      <div class="medium">of me</div>
    </div>
    <div class="thirteen">
      <div class="medium">Tea connoisseurs</div>
    </div>
    <div class="fourteen">
      <div class="medium">A possibly excessive</div>
      <div class="medium">amount of "BUBBY"</div>
    </div>
    <div class="center">
      <div class="fifteen">
        <div class="big">...and much</div>
        <div class="big highlight">more!!!</div>
      </div>
    </div>

    <div class="arrows">
      <i class="right fas fa-arrow-right" @click="nextSection()"></i>
    </div>
  </div>
</template>

<script>
export default {
  name: "Monologue",

  methods: {
    nextSection() {
      this.$refs.container.classList.add("fade-out")
      setTimeout(() => {
        this.$emit("next-section")
        console.log("emit")
      }, 1000)
    }
  }
}
</script>

<style lang="scss" scoped>

.section-7 {
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
  color: white;
}

.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);

  .one {
    opacity: 0;
    animation: fade-in-out 4s;
    animation-delay: 2s;
  }
  .two {
    opacity: 0;
    animation: fade-in-out 4s;
    animation-delay: 6.5s;
  }
  .fifteen {
    opacity: 0;
    animation: fade-in 1s;
    animation-delay: 37.5s;
    animation-fill-mode: forwards;
  }
}

.three {
  opacity: 0;
  position: absolute;
  top: 15%;
  left: 10%;
  animation: fade-in-out 4s;
  animation-delay: 11s;
}

.four {
  opacity: 0;
  position: absolute;
  top: 20%;
  right: 30%;
  animation: fade-in-out 4s;
  animation-delay: 13s;
}

.five {
  opacity: 0;
  position: absolute;
  bottom: 40%;
  left: 25%;
  animation: fade-in-out 4s;
  animation-delay: 15s;
}

.six {
  opacity: 0;
  position: absolute;
  bottom: 20%;
  right: 30%;
  animation: fade-in-out 4s;
  animation-delay: 17s;
}

.seven {
  opacity: 0;
  position: absolute;
  bottom: 45%;
  right: 20%;
  animation: fade-in-out 4s;
  animation-delay: 19s;
}

.eight {
  opacity: 0;
  position: absolute;
  bottom: 15%;
  left: 20%;
  animation: fade-in-out 4s;
  animation-delay: 21s;
}

.nine {
  opacity: 0;
  position: absolute;
  top: 35%;
  left: 30%;
  animation: fade-in-out 4s;
  animation-delay: 23s;
}

.ten {
  opacity: 0;
  position: absolute;
  top: 50%;
  left: 45%;
  animation: fade-in-out 4s;
  animation-delay: 25s;
}

.eleven {
  opacity: 0;
  position: absolute;
  top: 10%;
  right: 10%;
  animation: fade-in-out 4s;
  animation-delay: 27s;
}

.twelve {
  opacity: 0;
  position: absolute;
  top: 35%;
  left: 8%;
  animation: fade-in-out 4s;
  animation-delay: 29s;
}

.thirteen {
  opacity: 0;
  position: absolute;
  top: 7%;
  left: 40%;
  animation: fade-in-out 4s;
  animation-delay: 31s;
}

.fourteen {
  opacity: 0;
  position: absolute;
  bottom: 10%;
  right: 30%;
  animation: fade-in-out 4s;
  animation-delay: 33s;
}

</style>

