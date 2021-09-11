<template>
  <div class="poster-7">
    <div class="container">
      <div class="row">
        <div class="col-lg-6 order-lg-last">
          <div class="image p-5">
            <img :src="image" class="img-fluid pt-5" />
          </div>
        </div>
        <div class="col-lg-6 order-lg-first">
          <div class="context">
            <h2>Ipone12 pro is out now!</h2>
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. voluptate
              laborum numquam doloribus vero veritatis pariatur fuga voluptatum
              minus ipsum mollitia.
            </p>
            <div class="bullets mt-1">
              <img :src="img1" width="45" @click="image1" />
              <img :src="img2" width="45" @click="image2" />
              <img :src="img3" width="45" @click="image3" />
            </div>
            <button class="order-now">
              <i class="bi bi-handbag"></i> Order Now!
            </button>
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
  data() {
    return {
      image: require("@/assets/warehouse/banner/pic1.png"),
      img1: require("@/assets/warehouse/banner/pic1.png"),
      img2: require("@/assets/warehouse/banner/pic2.png"),
      img3: require("@/assets/warehouse/banner/pic3.png"),
    };
  },
  mounted() {
    gsap.to(".poster-7", {
      x: 0,
      duration: 1.5,
      scrollTrigger: {
        trigger: ".poster-7",
        toggleActions: "restart reverse restart reverse",
      },
    });
  },
  methods: {
    image1() {
      this.image = this.img1;
    },
    image2() {
      this.image = this.img2;
    },
    image3() {
      this.image = this.img3;
    },
  },
};
</script>

<style lang="scss" scoped>
.poster-7 {
  transform: translateX(100%);
  .image {
    overflow: hidden;
    position: relative;

    &::after {
      content: "";
      position: absolute;
      inset: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(17, 17, 17, 0.425);
      clip-path: circle(50% at center 120%);
      backdrop-filter: blur(8px);
      box-shadow: 5px 5px 50px rgb(17, 17, 17);
    }
  }
  .context {
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: flex-start;
    flex-direction: column;

    h2 {
      font-size: 3rem;
      text-transform: uppercase;
      font-weight: 600;
    }
    p {
      font-size: 0.9rem;
      width: 83%;
    }

    .bullets {
      img {
        margin: 5px;
        cursor: pointer;
        border: 3px solid transparent;
        width: 120px;
        padding: 10px;
        transition: 0.4s;

        &:hover {
          transform: translateY(-15px);
          border: 3px solid currentColor;
        }
      }
    }
    .order-now {
      padding: 10px 15px;
      border-radius: 30px;
      transition: all 0.3s ease-in-out;

      &:hover {
        background: #034586;
      }
    }
  }
}
/* Media Query */
@media (max-width: 768px) {
  .poster-7 {
    .image {
      display: flex;
      justify-content: center;
      align-items: center;
      margin-bottom: 30px;
      img {
        width: 60%;
      }
    }
    .context {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      align-items: center;

      h2 {
        font-size: 1.8rem;
      }
      p {
        font-size: 0.75rem;
        width: 100%;
        text-align: center;
      }
      .bullets {
        img {
          width: 100px;
        }
      }

      .order-now {
        padding: 10px 15px;
        border-radius: 30px;
        font-size: 0.8rem;
        letter-spacing: 1px;
      }
    }
  }
}
@media (max-width: 555px) {
  .poster-7 {
    .image {
      img {
        width: 85%;
      }
    }
    .context {
      h2 {
        font-size: 1.3rem;
      }
      .bullets {
        img {
          width: 85px;
        }
      }
    }
  }
}
</style>
