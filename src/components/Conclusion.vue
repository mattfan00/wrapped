<template>
  <div ref="container" class="section-8">
    <div class="center">
      <div class="one medium">Thank you for being the best part of every year for me. It still amazes me that someone loves me, cares about me, gets me thoughtful gifts, holds me at night, thinks I'm funny even when I'm not trying, and can just do nothing with me as much as you do. </div>
      <br>
      <div class="two medium">The past month gave me some outlook into how living with you will be. There may be a bit more clothes strewn across the floor than I thought (jk), but I still can't wait to be with you everyday. Happy <span class="cross">one</span> two years bub. I love you more than anything.</div>
      <div class="three">
        <img class="first" src="@/assets/images/matt.jpg">
        <img src="@/assets/images/mer.jpg">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Conclusion",

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

.section-8 {
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

.highlight {
  color: #f5ad06;
}

.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);

  .one {
    opacity: 0;
    animation: fade-in 1s;
    animation-delay: 2s;
    animation-fill-mode: forwards;
  }
  .two {
    opacity: 0;
    animation: fade-in 1s;
    animation-delay: 8s;
    animation-fill-mode: forwards;
  }
  .three {
    margin-top: 40px;
    display: flex;
    justify-content: center;

    opacity: 0;
    animation: fade-in 1s;
    animation-delay: 14s;
    animation-fill-mode: forwards;

    .first {
      margin-right: 25px;
    }

    img {
      width: 150px;
      height: 200px;

      border-radius: 12px;
      box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }
  }
}

.cross {
  text-decoration: line-through #f5ad06;
}
</style>