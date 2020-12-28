<template>
  <div ref="container" class="section-2">
    <div class="content">
      <div class="big title">A trip down <span class="highlight">memory lane</span></div>
      <div class="grid">
        <div class="date">
          <div class="medium">Nov 16, 2018</div>
          <div class="medium highlight">Meet Cute</div>
          <div class="caption">This was our meet cute, when I first laid eyes on bubby screaming at a laptop screen. A beautiful sight.</div>
        </div>
        <div class="date">
          <div class="medium">Dec 18, 2018</div>
          <div class="medium highlight">Facetime!</div>
          <div class="caption">The first time we facetimed each other was definitely not the last. This eventful night was preceded by numerous snaps and Strawberry Matcha playbacks.</div>
        </div>
        <div class="date">
          <div class="medium">Jan 3/4, 2019</div>
          <div class="medium highlight">Anniversary</div>
          <div class="caption">Our official anniversary day. I fell for bub so fast and skipped the "I like you" phase and straight to the dating phase. Soon after I wanted to say "I love you", but waited as you know :)</div>
        </div>
        <div class="date">
          <div class="medium">Jan 26, 2019</div>
          <div class="medium highlight">First Date</div>
          <div class="caption">We already dated for almost a month, but just had our first date. You are the pad see ew to my curry (that was cheesy, and probably didn't make sense). I knew that you were special and the long distance would be worth it.</div>
        </div>
        <div class="date">
          <div class="medium">Feb 24, 2019</div>
          <div class="medium highlight">Chicken wing</div>
          <div class="caption">The day I had the best chicken wing ever at Madame Vo. Oh, and also the day that bubby knew that she wanted to be with me for a long time.</div>
        </div>
        <div class="date">
          <div class="medium">Mar 25, 2019</div>
          <div class="medium highlight">I love you</div>
          <div class="caption">Bub's birthday, woohoo!</div>
        </div>
        <div class="date">
          <div class="medium">Jul 5, 2019</div>
          <div class="medium highlight">Cali vibes</div>
          <div class="caption">First trip to California! I want to go back and eat good food and chill in the sun with bub.</div>
        </div>
        <div class="date">
          <div class="medium">Nov 8, 2020</div>
          <div class="medium highlight">Living together</div>
          <div class="caption">A month long excursion to Ithaca. There is a huge time gap between this date and the last one because I have too many dates and didn't plan this well enough. I want to live with bub.</div>
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
  name: "Timeline",

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

.section-2 {
  position: absolute;
  height: 100vh;
  width: 100vw;
  color: black;
  z-index: 10;
  display: flex;
  justify-content: center;
  align-items: center;

  .content {
    width: 1000px;

    .grid {
      opacity: 0;
      margin-top: 40px;
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      grid-template-rows: repeat(2, 1fr);
      grid-gap: 40px;

      animation: fade-in 1s;
      animation-delay: 4s;
      animation-fill-mode: forwards;

      .date {
        .caption {
          margin-top: 10px;
        }
      }
    }
  }
}

.fade-out {
  animation: fade-out 1s;
  animation-fill-mode: forwards;
}

.title {
  opacity: 0;
  animation: fade-in 1s;
  animation-delay: 2s;
  animation-fill-mode: forwards;
}

.highlight {
  color: white;
}

</style>