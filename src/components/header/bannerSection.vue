<template>
  <div class="banner">
    <transition name="headline" appear="">
      <div class="context text-center">
        <h3>iPhone 12 Pro and iPhone 12 Pro Max</h3>
        <h2>It’s a leap year.</h2>
      </div>
    </transition>
    <video src="@/assets/banner.mp4" autoplay="">
      Your browser doesn't support this videos
    </video>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.banner {
  min-height: 70vh;

  .context {
    color: #fff;

    transform: translateY(100px);
    h3 {
      font-size: 1.5rem;
    }
    h2 {
      font-size: 5rem;
      font-weight: 600 !important;
      text-transform: uppercase;
    }
  }

  video {
    width: 90%;
    height: 90%;
    object-fit: cover;
  }
}

// transition

.headline-enter-from,
.headline-leave-to {
  opacity: 0;
}
.headline-enter-active,
.headline-leave-active {
  transition: all 0.5s ease-in-out 3s;
}

/* Media Query */
@media (max-width: 768px) {
  .banner {
    min-height: auto;

    .context {
      transform: translateY(30px);
      h3 {
        font-size: 0.9rem;
      }
      h2 {
        font-size: 2.2rem;
      }
    }

    video {
      width: 100%;
      height: 100%;
    }
  }
}
</style>
