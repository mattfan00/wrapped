<template>
  <div ref="container" class="section-2">
    timeline

    <div class="arrows">
      <i class="right fas fa-arrow-right" @click="nextSection()"></i>
    </div>
  </div>
</template>

<script>
export default {
  name: "Timeline",

  methods: {
    nextSection() {
      this.$refs.container.classList.add("fade-out")
      setTimeout(() => {
        this.$emit("next-section")
        console.log("emit")
      }, 1500)
    }
  }

}
</script>

<style lang="scss">

.section-2 {
  position: absolute;
  height: 100vh;
  width: 100vw;
  color: white;
  z-index: 10;
}

</style>