<template>
  <div ref="container" class="section-4">
    <div class="center">
      <div class="first">
        <div class="big">To pass</div>
        <div class="big">the <span class="highlight">time,</span></div>
      </div>
    </div>
    <div class="center">
      <div class="second">
        <div class="big">You shared with me</div>
        <div class="big">a lot of great</div>
        <div class="big"><span class="highlight">movies</span> and <span class="highlight">shows</span></div>
      </div>
    </div>
    <div class="center">
      <div class="third">
        <div class="big">Here are my</div>
        <div class="big highlight">thoughts</div>
      </div>
    </div>
    <div class="ratings fourth">
      <div class="content">
        <div class="big title">Matt's <span class="highlight">Review Corner</span></div>
        <div class="middle">
          <div class="grid-1">
            <div class="movie">
              <div class="medium"><span class="highlight">1.</span> Chef</div>
              <div class="caption">A beautiful, inspirational, and exciting underdog story. From the start, Chef has you rooting for the main characters and praying for their success. Plus it features food. My favorite memory was losing my phone in the crack of doom and bubby getting her arm stuck.</div>
            </div>
            <div class="movie">
              <div class="medium"><span class="highlight">2.</span> The Big Sick</div>
              <div class="caption">An obvious fan favorite, this feel good movie is full of emotion, love, and laughter. One of the few movies we have rewatched together. Bub knows her rom-coms.</div>
            </div>
            <div class="movie">
              <div class="medium"><span class="highlight">3.</span> The Boys</div>
              <div class="caption">Don't let the gore and violence deter you from this show, The Boys is a plot-driven superhero show that excellently establishes a bond between you and all characters, even the villains. Not a typical show we would watch together, but one I always look forward to.</div>
            </div>
          </div>
          <div class="grid-2">
            <div class="movie">
              <div class="medium"><span class="highlight">4.</span> Kim's Convenience</div>
              <div class="caption">Kim's Convenience is an entertaining sitcom taking place at a small convenience store in Toronto. It makes you wonder, am I watching this show because it's good or because I like staring at one of the male characters (who will not be named)? Nevertheless, I would recommend this show to anybody, and it holds a special place in this relationship since its the first show we watched together.</div>
            </div>
            <div class="movie">
              <div class="medium"><span class="highlight">5.</span> Lovebirds</div>
              <div class="caption">Does this movie make sense? No. Are you watching this for the plot? No. Why are you watching it? Because it's funny. Lovebirds is a very entertaining and hilarious feel-good rom-com and is guarenteed to get a laugh out of anyone. I very much enjoyed seeing bub laughing hysterically the whole time.</div>
            </div>
          </div>
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
  name: "Movies",

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

.section-4 {
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
  color: #3b01e2;
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
    opacity: 0;
    animation: fade-in-out 4s;
    animation-delay: 6.5s;
  }
  .third {
    opacity: 0;
    animation: fade-in-out 4s;
    animation-delay: 11s;
  }
}

.fourth {
  opacity: 0;
  animation: fade-in 1s;
  animation-delay: 15.5s;
  animation-fill-mode: forwards;
}

.ratings {
  height: 100vh;
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;

  .content {
    width: 1000px;

    .title {
      opacity: 0;
      animation: fade-in 1s;
      animation-delay: 2s;
      animation-fill-mode: forwards;
    }

    .middle{
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-top: 40px;
    }

    .movie {
      .caption {
        margin-top: 10px;
      }
    }

    .grid-1 {
      display: grid;
      grid-template-columns: repeat(3, 275px);
      grid-gap: 40px;
    }

    .grid-2 {
      margin-top: 40px;
      display: grid;
      grid-template-columns: repeat(2, 275px);
      grid-gap: 40px;
    }
  }

}

</style>