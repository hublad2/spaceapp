<template>
  <div class="wrapper">
    <div class="background"></div>
    <TheHero />
    <TheSlide1Relic />
    <TheSlide2Proton />
    <TheSlide3Nucleus />
    <TheSlide4Dark />
    <TheSlide5Galaxy />
    <TheSlide6StarsSmall />
    <TheSlide7StarsMedium />
    <TheSlide8StarsBig />
    <TheSlide9Now />
    <TheSlide10Begining />
    <TheSlide11Sun />
    <TheSlide11Corona />
    <TheSlide12Mercury />
    <TheSlide13Venus />
    <TheSlide14Earth />
    <TheSlide15Mars />
    <TheSlide16Jupiter />
    <TheSlide17Saturn />
    <TheSlide18Uranus />
    <TheSlide19Neptune />
    <TheSlide21AfterNeptune />
    <TheSlide22FinalShock />
    <TheSlide23Oort />
    <TheSlide24Neighbourhood />
    <TheSlide20SystemEnd />
    <TheSlide25OurGalaxy />
    <TheSlide26Local />
    <TheSlide27Supergroup />
    <TheSlide28Hubble />
    <TheSlide29End />
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
import TheSlide6StarsSmall from "@/components/TheSlide6StarsSmall.vue";
import TheSlide7StarsMedium from "@/components/TheSlide7StarsMedium.vue";
import TheSlide8StarsBig from "@/components/TheSlide8StarsBig.vue";
import TheSlide9Now from "@/components/TheSlide9Now.vue";
import TheSlide10Begining from "@/components/TheSlide10Begining.vue";
import TheSlide11Sun from "@/components/TheSlide11Sun.vue";
import TheSlide11Corona from "@/components/TheSlide11Corona.vue";
import TheSlide12Mercury from "@/components/TheSlide12Mercury.vue";
import TheSlide13Venus from "@/components/TheSlide13Venus.vue";
import TheSlide14Earth from "@/components/TheSlide14Earth.vue";
import TheSlide15Mars from "@/components/TheSlide15Mars.vue";
import TheSlide16Jupiter from "@/components/TheSlide16Jupiter.vue";
import TheSlide17Saturn from "@/components/TheSlide17Saturn.vue";
import TheSlide18Uranus from "@/components/TheSlide18Uranus.vue";
import TheSlide19Neptune from "@/components/TheSlide19Neptune.vue";
import TheSlide20SystemEnd from "@/components/TheSlide20SystemEnd.vue";
import TheSlide21AfterNeptune from "@/components/TheSlide21AfterNeptune.vue";
import TheSlide22FinalShock from "@/components/TheSlide22FinalShock.vue";
import TheSlide23Oort from "@/components/TheSlide23Oort.vue";
import TheSlide24Neighbourhood from "@/components/TheSlide24Neighbourhood.vue";
import TheSlide25OurGalaxy from "@/components/TheSlide25OurGalaxy.vue";
import TheSlide26Local from "@/components/TheSlide26Local.vue";
import TheSlide27Supergroup from "@/components/TheSlide27Supergroup.vue";
import TheSlide28Hubble from "@/components/TheSlide28Hubble.vue";
import TheSlide29End from "@/components/TheSlide29End.vue";

export default {
  name: "Home",
  components: {
    TheHero,
    TheSlide1Relic,
    TheSlide2Proton,
    TheSlide3Nucleus,
    TheSlide4Dark,
    TheSlide5Galaxy,
    TheSlide6StarsSmall,
    TheSlide7StarsMedium,
    TheSlide8StarsBig,
    TheSlide9Now,
    TheSlide10Begining,
    TheSlide11Sun,
    TheSlide11Corona,
    TheSlide12Mercury,
    TheSlide13Venus,
    TheSlide14Earth,
    TheSlide15Mars,
    TheSlide16Jupiter,
    TheSlide17Saturn,
    TheSlide18Uranus,
    TheSlide19Neptune,
    TheSlide20SystemEnd,
    TheSlide21AfterNeptune,
    TheSlide22FinalShock,
    TheSlide23Oort,
    TheSlide24Neighbourhood,
    TheSlide25OurGalaxy,
    TheSlide26Local,
    TheSlide27Supergroup,
    TheSlide28Hubble,
    TheSlide29End,
  },
  data() {
    return {
      results: [],
    };
  },
};
</script>

<style lang="scss" scoped>
.wrapper {
  overflow-y: hidden;
  max-width: 1400px;
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
