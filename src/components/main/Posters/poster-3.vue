<template>
  <div class="poster-3">
    <div class="container">
      <div class="image">
        <img src="@/assets/3lg.jpg" class="d-none d-sm-block" />
        <img src="@/assets/3sm.jpg" class="d-block d-sm-none" />
      </div>
      <div class="context text-center">
        <h2>Make Your Selfie More Fun!</h2>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut omnis
          modi quidem libero deserunt quas accusamus odit porro minus
          consequuntur obcaecati reiciendis fuga, tempore, veniam suscipit
          quibusdam, eos magnam voluptatibus.
        </p>
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
    gsap.to(".poster-3", {
      x: 0,
      scale: 1,
      opacity: 1,
      scrollTrigger: {
        trigger: ".poster-3",
        scrub: 0.3,
        toggleActions: "restart reverse restart reverse",
      },
    });
  },
};
</script>

<style lang="scss" scoped>
.poster-3 {
  margin-top: 60px;
  transform: translateX(100px) scale(0.6);
  opacity: 0;
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;

    .image {
      img {
        width: 100%;
        height: 100%;
        object-fit: contain;
      }
    }
    .context {
      h2 {
        font-weight: 900;
        font-size: 3rem;
      }
    }
  }
}
/* Media Query */
@media (max-width: 768px) {
  .poster-3 {
    margin-top: 0;
    .container {
      .context {
        h2 {
          font-size: 2rem;
        }
        p {
          font-size: 0.75rem;
        }
      }
    }
  }
}
</style>
