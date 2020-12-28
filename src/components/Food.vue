<template>
  <div ref="container" class="section-3">
    <div class="center">
      <div class="first">
        <div class="big">Throughout our</div>
        <div class="big highlight">journey,</div>
      </div>
    </div>
    <div class="center">
      <div class="second">
        <div class="big">We ate a</div>
        <div class="big">lot of <span class="highlight">food</span></div>
      </div>
    </div>
    <div class="center">
      <div class="third">
        <div>
            <div class="big">There are <span class="highlight">28</span></div>
            <div class="big">food pics on</div>
            <div class="big">my phone</div>
            <div class="small">I had a lot of fun taking them</div>
        </div>
        <img src="@/assets/images/foodpic.jpg">
      </div>
    </div>
    <div class="center">
      <div class="fourth">
        and we ate at oishii bowl at least 6 times
      </div>
    </div>

    <div class="arrows">
      <i class="right fas fa-arrow-right" @click="nextSection()"></i>
    </div>
  </div>
</template>

<script>

export default {
  name: "Food",

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

.section-3 {
  position: absolute;
  height: 100vh;
  width: 100vw;
  color: white;
  z-index: 10;
}

.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);

  .highlight {
    color: #fff703;
  }

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
  .third {
    display: flex;
    align-items: center;

    opacity: 0;
    animation: fade-in-out-long 6s;
    animation-delay: 11s;

    img {
      margin-left: 80px;
      width: 175px;
      height: 233.3333px;

      border-radius: 12px;
      box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);

    }
  }
  .fourth {
    opacity: 0;
    animation: fade-in 1s;
    animation-delay: 17.5s;
    animation-fill-mode: forwards;
  }
}

</style>