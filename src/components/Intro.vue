<template>
  <div ref="container" class="section-1">
    <div class="center">
      <div class="first">
        <div class="big">Hi,</div>
        <div class="big highlight">Bubby</div>
      </div>
    </div>
    <div class="center">
      <div class="second">
        <div class="big">Welcome to</div>
        <div class="big">your <span class="highlight">Relationship</span></div>
        <div class="big highlight">Wrapped</div>
        <div class="small">
          (use the arrow button to continue)
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
  name: 'Intro',

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

.section-1 {
  position: absolute;
  height: 100vh;
  width: 100vw;
  color: white;
  z-index: 10;
}

.fade-out {
  animation: fade-out 1s;
  animation-fill-mode: forwards;
}

.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);

  .highlight {
    color: #f5ad06;
  }

  .first {
    opacity: 0;
    animation: fade-in-out 4s;
  }
  .second {
    opacity: 0;
    animation: fade-in 1s;
    animation-delay: 4.5s;
    animation-fill-mode: forwards;
  }
}

</style>