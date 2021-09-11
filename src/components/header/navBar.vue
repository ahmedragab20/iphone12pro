<template>
  <div class="nav">
    <div class="container">
      <figure class="upper" :class="{ active: isActive }">
        <div class="links">
          <div class="logo">
            <img src="@/assets/apple.svg" width="30" />
          </div>
          <div>Mac</div>
          <div>iPad</div>
          <div>iPhone</div>
          <div>Watch</div>
          <div>TV</div>
          <div>Music</div>
          <div>Support</div>
          <div>Where to Buy</div>
          <div class="search">
            <i class="bi bi-search" @click="searchInput"></i>
          </div>
        </div>

        <section class="search-input" @click.self="searchInput">
          <form @submit.prevent>
            <input type="text" placeholder="Search Input ..." />
            <i class="bi bi-search" @click="searchInput"></i>
          </form>
        </section>
      </figure>
      <figure class="under">
        <div class="left w-50">
          <h1>iPhone 12 Pro</h1>
        </div>
        <div class="right w-50">
          <div class="content w-50">
            <h3 class="active">Overview</h3>
            <h3>Tech Specs</h3>
            <button>Buy</button>
          </div>
        </div>
      </figure>
    </div>
  </div>
</template>

<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

export default {
  mounted() {
    ScrollTrigger.create({
      start: "top 8vh",
      trigger: ".nav",
      toggleClass: { targets: ".under", className: "nav-active" },
    });
  },
  data() {
    return {
      isActive: false,
    };
  },
  methods: {
    searchInput() {
      this.isActive = !this.isActive;
    },
  },
};
</script>

<style lang="scss" scoped>
.nav {
  min-height: 8vh;
  position: relative;

  .upper {
    position: relative;

    .links {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 10px 0;
      transition: all 0.5s ease-in-out;

      div {
        opacity: 0.8;
        font-size: 0.9rem;
        transition: 0.4s;
        cursor: pointer;

        &:hover {
          opacity: 1;
        }
      }
    }

    .search-input {
      position: absolute;
      top: 0px;
      height: 8vh;
      padding: 10px 0;
      transform: scale(0);
    }

    &.active {
      position: relative;

      .links {
        transform: scale(0);
        position: absolute;
        width: 100%;
        padding: 10px 10%;
      }

      .search-input {
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        position: relative;
        transform: scale(1);
        transition: all 0.5s ease-in-out 0.5s;

        &::after {
          content: "X";
          position: absolute;
          left: 0;
          display: flex;
          justify-content: center;
          align-items: center;
          width: 30px;
          height: 30px;
          background-color: #161617;
          border-radius: 50%;
          cursor: pointer;
        }

        form {
          width: 80%;
          display: flex;
          justify-content: flex-end;
          align-items: center;
          margin-left: auto;

          input {
            width: 80%;
            border-radius: 20px;
            padding: 5px 10px;
            caret-color: currentColor;
            position: relative;
            margin-right: -10px;
            font-size: 0.9rem;
          }

          i {
            position: absolute;
          }
        }
      }
    }
  }
  .under {
    z-index: 99;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    padding: 10px 11%;
    transition: all 1s ease;
    -webkit-backdrop-filter: blur(8px);
    -moz-backdrop-filter: blur(8px);
    -ms-backdrop-filter: blur(8px);
    -o-backdrop-filter: blur(8px);
    backdrop-filter: blur(8px);
    background-color: #161617f3;

    &.nav-active {
      position: relative;
      width: 100%;
      padding: 0;
      background-color: transparent;
    }

    .left {
      h1 {
        font-size: 1.2rem;
        cursor: pointer;
      }
    }
    .right {
      display: flex;
      justify-content: flex-end;
      align-items: center;

      .content {
        display: flex;
        justify-content: space-between;
        align-items: center;

        h3 {
          font-size: 0.9rem;
          cursor: pointer;

          &.active {
            opacity: 0.7;
            pointer-events: none;
          }
        }

        button {
          padding: 2px 15px;
          border-radius: 20px;
          transition: 0.3s;

          &:hover {
            background: #034586;
          }
        }
      }
    }
  }
}
/* Media Query */
@media (max-width: 768px) {
  .nav {
    .under {
      .left {
        h1 {
          font-size: 1rem;
        }
      }
      .right {
        .content {
          width: 60% !important;

          h3 {
            font-size: 0.75rem;
            transform: translateY(3px);
          }

          button {
            padding: 1px 10px;
            font-size: 0.75rem;
          }
        }
      }
    }
  }
}
@media (max-width: 555px) {
  .nav {
    .upper {
      display: none;
    }
    .under {
      &.nav-active {
        margin-top: 10px;
      }
      .right {
        .content {
          width: 50% !important;

          h3 {
            display: none;
          }

          button {
            margin-left: auto;
          }
        }
      }
    }
  }
}
</style>
