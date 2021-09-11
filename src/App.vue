<template>
  <div class="app">
    <header>
      <nav>
        <nav-bar />
      </nav>
      <banner-section />
    </header>
    <main>
      <poster-1 />
      <video-1 />
      <poster-2 />
      <poster-3 />
      <poster-4 />
      <poster-5 />
      <poster-6 />
      <poster-7 />
    </main>
    <footer>
      <mainFooter />
    </footer>
  </div>
</template>

<script>
import navBar from "@/components/header/navBar.vue";
import bannerSection from "@/components/header/bannerSection.vue";
import Poster1 from "./components/main/Posters/poster-1.vue";
import Video1 from "./components/main/Videos/video-1.vue";
import Poster2 from "./components/main/Posters/poster-2.vue";
import Poster3 from "./components/main/Posters/poster-3.vue";
import Poster4 from "./components/main/Posters/poster-4.vue";
import Poster5 from "./components/main/Posters/poster-5.vue";
import Poster6 from "./components/main/Posters/poster-6.vue";
import Poster7 from "./components/main/Posters/poster-7.vue";
import mainFooter from "@/components/Footer/mainFooter.vue";

export default {
  name: "App",
  components: {
    navBar,
    bannerSection,
    Poster1,
    Video1,
    Poster2,
    Poster3,
    Poster4,
    Poster5,
    Poster6,
    Poster7,
    mainFooter,
  },
};
</script>

<style lang="scss"></style>
