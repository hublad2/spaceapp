<template>
  <div class="wrapper">
    <div class="background"></div>
    <TheHero />
    <TheSlide1Relic />
    <TheSlide2Proton />
    <TheSlide3Nucleus />
    <TheSlide4Dark />
    <TheSlide5Galaxy />
  </div>
</template>

<script>
// @ is an alias to /src
import TheHero from "@/components/TheHero.vue";
import TheSlide1Relic from "@/components/TheSlide1Relic.vue";
import TheSlide2Proton from "@/components/TheSlide2Proton.vue";
import TheSlide3Nucleus from "@/components/TheSlide3Nucleus.vue";
import TheSlide4Dark from "@/components/TheSlide4Dark.vue";
import TheSlide5Galaxy from "@/components/TheSlide5Galaxy.vue";

export default {
  name: "Home",
  components: {
    TheHero,
    TheSlide1Relic,
    TheSlide2Proton,
    TheSlide3Nucleus,
    TheSlide4Dark,
    TheSlide5Galaxy,
  },
};
</script>

<style lang="scss" scoped>
.wrapper {
  overflow-y: hidden;
}

.background {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: -3;
  background: linear-gradient(180deg, #0d1922 0%, rgba(15, 38, 51, 0.95) 100%);
}
</style>
