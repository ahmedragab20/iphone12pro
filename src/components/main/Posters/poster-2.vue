<template>
  <div class="poster-2">
    <div class="container">
      <div class="grid-container">
        <section class="left">
          <figure>
            <h4>Up to</h4>
            <h3>1200nits</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Itaque
              facilis molestiae excepturi, asperiores soluta aliquid.
            </p>
          </figure>
        </section>
        <section class="center">
          <video src="@/assets/v-2.mp4" autoplay loop></video>
        </section>
        <section class="right">
          <figure>
            <h3>2,000,000:1</h3>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Itaque
              facilis molestiae excepturi, asperiores soluta aliquid.
            </p>
          </figure>
        </section>
      </div>
    </div>
  </div>
</template>

<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);
export default {
  mounted() {
    gsap.to(".poster-2", {
      opacity: 1,
      scale: 1,
      duration: 1,
      scrollTrigger: {
        trigger: ".poster-2",
        toggleActions: "restart reverse restart reverse",
      },
    });
  },
};
</script>

<style lang="scss" scoped>
.poster-2 {
  opacity: 0;
  transform: scale(0);
  .grid-container {
    display: grid;
    grid-template-columns: repeat(auto, 1fr);
    grid-template-areas: "left center right";
    gap: 10px;

    video {
      pointer-events: all !important;
    }
    section {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;

      figure {
        background-color: #161617;
        border-radius: 10px;
        padding: 10px 15px;
        h4 {
          font-weight: 600;
        }
        h3 {
          font-weight: 600;
          background: linear-gradient(to right, #005e7f, #61b6cd);
          -webkit-background-clip: text;
          background-clip: text;
          -webkit-text-fill-color: transparent;
          font-size: 2.3rem;
        }
        p {
          font-size: 0.75rem;
        }
      }
    }

    .left {
      grid-area: left;
    }
    .center {
      grid-area: center;
    }
    .right {
      grid-area: right;
    }
  }
}

@media (max-width: 1024px) {
  .poster-2 {
    .grid-container {
      grid-template-areas:
        ". center ."
        ". left ."
        ". right .";
    }
  }
}
/* Thanks Display Grid */
</style>
