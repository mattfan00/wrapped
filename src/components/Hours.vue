<template>
  <div ref="container" class="section-5">
    <div class="center">
      <div class="first">
        <div class="big">Math</div>
        <div class="big highlight">break!</div>
      </div>
    </div>
    <div class="center">
      <div class="second">
        <div class="medium">Let's first assume that out of all of the days we dated, we called 2/3 of the days. So that is 730 * 2/3, which is around <span class="highlight">487 hours.</span></div>
        <br>
        <div class="medium">However, during the breaks and some other days we are able to call longer, so lets say that for 50 days in the year, we can call for 2 hours instead of 1 hour. So we add 100 to 487 to get <span class="highlight">587 hours.</span></div>
        <br>
        <div class="medium">This doesn't take into account the time we see each other. So lets say there are 30 days in the year that we can spend 24 hours together, so we add 720 to 587 and get <span class="highlight">1307 hours.</span></div>
      </div>
    </div>
    <div class="center">
      <div class="third">
        <div class="big highlight">1307 hours</div>
        <div class="small">This might not be as much as other couples who have been together for 2 years, but I our time will come when we can be together all the time and we are going to make this number much larger :)</div>
        <div class="small">Maybe like one third of these hours had some snippet of me singing so I'm sorry bub.</div>
      </div>
    </div>

    <div class="arrows">
      <i class="right fas fa-arrow-right" @click="nextSection()"></i>
    </div>
  </div>
</template>

<script>

export default {
  name: "Hours",

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

.section-5 {
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
  color: #a5ffee;
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
    width: 600px;
    opacity: 0;
    animation: fade-in-out-xlong 20s;
    animation-delay: 6.5s;
  }
  .third{
    width: 400px;
    opacity: 0;
    animation: fade-in 1s;
    animation-delay: 27s;
    animation-fill-mode: forwards;
  }
}
</style>