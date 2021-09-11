<template>
  <div class="nav">
    <div class="logo">
      <img src="@/assets/global/logo.svg" width="35" />
    </div>
    <div class="left">
      <div class="links" :class="{ active: isActive }">
        <ul>
          <li class="active">Home</li>
          <li>Services</li>
          <li>Products</li>
          <li>Gallery</li>
          <li>About</li>
        </ul>
      </div>
      <button class="store">
        <img src="@/assets/global/sale.svg" width="25" />
      </button>
      <div class="burger" @click="isActive = !isActive">
        <div></div>
        <div></div>
        <div></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: false,
    };
  },
};
</script>

<style lang="scss" scoped>
.nav {
  z-index: 9;
  padding: 0 6.5%;
  min-height: 10vh;
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  backdrop-filter: blur(8px);
  display: flex;
  justify-content: space-between;
  align-items: center;
  .left {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 60%;
    height: 10vh;
    .links {
      width: 90%;
      height: 10vh;
      transition: 0.5s;

      ul {
        height: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;

        li {
          cursor: pointer;
          font-weight: 600;

          &.active {
            text-decoration: underline;
          }

          &:hover {
            text-decoration: underline;
          }
        }
      }
    }
    .store {
      width: 40px;
      height: 40px;
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
      transition: 0.3s;

      &:hover {
        box-shadow: none;

        &::after {
          transform: scale(1);
        }
      }

      &::after {
        content: "Store";
        position: absolute;
        top: -15px;
        padding: 5px;
        background-color: rgba(17, 17, 17, 0.9);
        border-radius: 8px;
        color: #fff;
        pointer-events: none;
        font-weight: 600;
        transform: scale(0);
        transition: 0.3s;
      }
    }

    .burger {
      width: 40px;
      height: 40px;
      cursor: pointer;
      display: none;
      box-shadow: 2px 2px 5px rgba(17, 17, 17, 0.2),
        -2px -2px 5px rgba(17, 17, 17, 0.2);
      border-radius: 50%;
      transition: 0.3s;

      &:hover {
        box-shadow: none;
      }

      div {
        margin: 2.5px;
        background-color: currentColor;
        height: 1px;
        width: 25px;
      }
    }
  }
}
/* Media Query */
@media (max-width: 768px) {
  .nav {
    .left {
      justify-content: flex-end;
      gap: 10px;

      .links {
        width: 50vw;
        height: 90vh;
        display: grid;
        place-items: center;
        position: absolute;
        top: 10vh;
        right: -100vw;
        background-color: rgb(255, 255, 255);
        box-shadow: -10px 5px 10px rgba(0, 0, 0, 0.192);

        &.active {
          right: 0;
        }
        ul {
          flex-direction: column;
          justify-content: center;
          width: 100%;
          height: 60vh;
          display: grid;
          place-items: center;
        }
      }

      .burger {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
      }
    }
  }
}

@media (max-width: 555px) {
  .nav {
    .left {
      .links {
        width: 85%;
      }
    }
  }
}
</style>
