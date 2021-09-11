<template>
  <div class="banner">
    <div class="container">
      <div class="row">
        <div class="col-lg-6 order-lg-last">
          <div class="image p-5">
            <transition name="bullets" appear>
              <img :src="image" class="img-fluid pt-5" />
            </transition>
          </div>
        </div>
        <div class="col-lg-6 order-lg-first">
          <div class="context">
            <h2>Ipone12 pro is out now!</h2>
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque,
              voluptate laborum numquam doloribus vero veritatis pariatur fuga
              voluptatum minus ipsum mollitia id laudantium temporibus, vel
              aperiam nisi corporis iste ipsam!
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
export default {
  data() {
    return {
      image: require("@/assets/banner/pic1.png"),
      img1: require("@/assets/banner/pic1.png"),
      img2: require("@/assets/banner/pic2.png"),
      img3: require("@/assets/banner/pic3.png"),
    };
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
.banner {
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
        transition: 0.3s;

        &:hover {
          transform: translateY(-10px);
          border: 3px solid currentColor;
        }
      }
    }
    .order-now {
      padding: 10px 15px;
      border-radius: 10px;
      background-color: transparent;

      &,
      i {
        transition: 0.5s;
      }

      &:hover {
        background-color: #010101;
        box-shadow: none;
        &,
        i {
          color: #fff;
        }
      }
    }
  }
}
/* Media Query */
@media (max-width: 768px) {
  .banner {
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
      align-items: center;
      h2 {
        font-size: 1.8rem;
      }
      p {
        font-size: 0.75rem;
        width: 100%;
      }
      .bullets {
        img {
          width: 100px;
        }
      }
    }
  }
}
@media (max-width: 555px) {
  .banner {
    .image {
      img {
        width: 85%;
      }
    }
    .context {
      h2 {
        font-size: 1.3rem;
      }
      p {
        font-size: 0.75rem;
        width: 100%;
        text-align: center;
      }
      .bullets {
        img {
          width: 85px;
        }
      }
    }
  }
}
/* transition */
.bullets-enter-from,
.bullets-leave-to {
  transform: scale(0);
  opacity: 0;
}
.bullets-enter-active,
.bullets-leave-active {
  transition: all 1s ease-in-out;
}
</style>
