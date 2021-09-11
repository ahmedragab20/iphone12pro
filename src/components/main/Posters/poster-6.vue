<template>
  <div class="poster-6">
    <div class="container">
      <div class="image">
        <img src="@/assets/2.jpg" class="d-none d-sm-block" />
        <img src="@/assets/2-2.jpg" class="d-block d-sm-none" />
      </div>
      <div class="context text-center">
        <h2>It's More Than Just Camera</h2>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut omnis
          modi quidem libero deserunt quas.
        </p>
        <div class="icons">
          <div class="one"><i class="bi bi-power"></i>More aspernatur</div>
          <div class="two"><i class="bi bi-watch"></i> ea exercitation</div>
          <div class="three"><i class="bi bi-plug"></i> ducimus tempore</div>
          <div class="four"><i class="bi bi-pin"></i> unde suscipit</div>
        </div>
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
    gsap.to(".poster-6", {
      x: 0,
      scale: 1,
      opacity: 1,
      scrollTrigger: {
        trigger: ".poster-6",
        scrub: 0.3,
        toggleActions: "restart reverse restart reverse",
      },
    });
  },
};
</script>

<style lang="scss" scoped>
.poster-6 {
  transform: translateX(10px) scale(0.5);
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
      p {
        font-size: 0.75rem;
      }
      .icons {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-template-areas: "one two three four";
        grid-gap: 10px;

        .one {
          grid-area: one;
        }
        .two {
          grid-area: two;
        }
        .three {
          grid-area: three;
        }
        .four {
          grid-area: four;
        }

        div {
          padding: 10px 20px;
          background-color: #161617cc;
          border-radius: 5px;
          margin: 10px 0;
          font-weight: 600;
          cursor: pointer;
          transition: 0.3s;
          text-transform: capitalize;
          display: flex;
          justify-content: center;
          align-items: center;
          flex-direction: column;
          height: 110px;

          &:hover {
            background-color: #161617;
          }

          i {
            padding: 5px;
            cursor: pointer;
            font-size: 1.5rem;
          }
        }
      }
    }
  }
}
/* Media Query */
@media (max-width: 768px) {
  .poster-6 {
    .container {
      .context {
        h2 {
          font-size: 2rem;
        }
        p {
          font-size: 0.75rem;
        }
        .icons {
          grid-template-columns: repeat(2, 1fr);
          grid-template-areas:
            "one two"
            "three four";
          div {
            i {
              font-size: 1.1rem;
            }
          }
        }
      }
    }
  }
}
</style>
