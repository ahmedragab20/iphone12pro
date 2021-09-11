<template>
  <div class="video-1">
    <video src="@/assets/v-1.mp4" autoplay loop class="v-1"></video>
  </div>
</template>

<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);
export default {
  mounted() {
    gsap.to(".v-1", {
      y: 0,
      opacity: 1,
      scrollTrigger: {
        trigger: ".v-1",
        scrub: 0.2,
        toggleActions: "restart reverse restart reverse",
      },
    });
  },
};
</script>

<style lang="scss" scoped>
.video-1 {
  overflow: hidden;
  .v-1 {
    transform: translateY(-100%);
    opacity: 0.5;
    height: 100%;
    width: 100%;
    object-fit: cover;
  }
}
</style>
