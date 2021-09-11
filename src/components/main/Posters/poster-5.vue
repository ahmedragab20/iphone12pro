<template>
  <div class="poster-5 mt-5">
    <div class="container">
      <div class="row">
        <div class="col-lg-6">
          <div class="image">
            <img src="@/assets/5.jpg" class="img-fluid poster-5" />
          </div>
        </div>
        <div class="col-lg-6">
          <div class="content">
            <h2>Enjoy Your Pictures</h2>
            <h2 class="h1">
              Lorem ipsum dolor sit amet consectetur adipisicing elitNobis.
            </h2>
            <p>
              Lorem ipsum, dolor sit amet consectetur adipisicing elit. Beatae
              illum adipisci impedit dolore molestias nisi nulla enim eum
              similique velit, ducimus tempore aspernatur ea exercitationem
              assumenda totam repellat unde suscipit.
            </p>
            <div class="icons">
              <div><i class="bi bi-power"></i>Mpore aspernatur</div>
              <div><i class="bi bi-watch"></i> ea exercitation</div>
              <div><i class="bi bi-plug"></i> ducimus tempore</div>
              <div><i class="bi bi-pin"></i> unde suscipit</div>
            </div>
          </div>
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
    gsap.to(".poster-5", {
      x: 0,
      duration: 1.5,
      scrollTrigger: {
        trigger: ".poster-5",
        toggleActions: "restart reverse restart reverse",
      },
    });
  },
};
</script>

<style lang="scss" scoped>
.poster-5 {
  transform: translateX(-100%);

  .image {
    img {
      border-radius: 10px !important;
    }
  }

  .content {
    h2 {
      background: linear-gradient(to right, #005e7f, #61b6cd);
      -webkit-background-clip: text;
      background-clip: text;
      -webkit-text-fill-color: transparent;
    }
    .h1 {
      font-size: 2rem;
      font-weight: 600;
      color: #fff;
    }

    .icons {
      div {
        padding: 10px;
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
        float: left;
        margin: 5px;
        width: 45%;
        height: 150px;

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

/* Media Query */

@media (max-width: 768px) {
  .poster-5 {
    text-align: center;
    padding: 30px 0;

    .content {
      h2 {
        font-size: 1rem;
      }
      .h1 {
        font-size: 1.3rem;
        font-weight: 600;
        color: #fff;
      }
      p {
        font-size: 0.75rem;
      }

      .icons {
        div {
          i {
            font-size: 1.1rem;
          }
        }
      }
    }
  }
}
</style>
