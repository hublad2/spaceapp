<template>
  <section class="slide">
    <div class="slide__star-hero">
      <h1>Początek układu</h1>
    </div>
    <div class="slide__caption">
      <h2>Dysk protoplanetarny</h2>
    </div>
    <div class="slide__image">
      <img
        src="../assets/Digitized_Sky_Survey_Image_of_Betelgeuse.jpg"
        alt="Betelgeza"
      />
    </div>
    <div class="slide__tile-text">
      <p>
        Czasami, gdy gwiazda kończy życie, robi to z nielada rozmachem. Wyrzuca
        z siebie ogromne ilości materii i energii w przestrzeń, a sama pozostaje
        gwiazdą neutronową albo czarną dziurą. Wyrzut tej materii generuje ze
        sobą falę uderzeniową.
      </p>
    </div>
    <div class="slide__tile-text2">
      <p>
        Przewiduje się, że właśnie jedna z takich fal uderzeniowych dotarła do
        układy słonecznego - który był wtedy jeszcze obłokiem gazu - i zagęściła
        go, co zapoczątkowało proces powstawanie naszej gwiazdy - Słońca, oraz
        planet.
      </p>
    </div>
    <div class="slide__tile-fill"></div>
    <div class="slide__tile-fill2"></div>
    <div class="slide__tile-fill3"></div>
  </section>
</template>

<script>
export default {
  name: "TheSlide10Begining",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide {
  @extend %slide-settings;
  grid-template-rows: repeat(20, 16.6666vw);
  grid-template-areas:
    "hero hero hero hero hero .   "
    "hero hero hero hero hero .   "
    ".    .    .    .    .    .   "
    ".    .    .    cap  cap  cap "
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "text text text text text .  "
    "text text text text text .  "
    "text text text text text .  "
    "text text text text text  fil2 "
    "text text text text text  fil2 "
    "fil   fil    fil    fil    fil    fil   "
    " fil3   text2   text2 text2 text2 text2"
    "  fil3  text2   text2 text2 text2 text2"
    ".    text2   text2 text2 text2 text2"
    ".    text2   text2 text2 text2 text2"
    ".    text2   text2 text2 text2 text2"
    ".    .    .    .    .    .   ";

  &__star-hero {
    grid-area: hero;
    @extend %tile-gray-header;
    /* @extend %tile-white-header; */
    /*  @extend %tile-white; */
    /* @extend %tile-gray; */
    font-size: 8vw;
  }

  &__caption {
    grid-area: cap;
    font-size: 5vw;
    @extend %tile-white;
    /* @extend %tile-purple; */
  }

  &__image {
    grid-area: img;
    display: flex;
    justify-content: center;
    align-items: center;

    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  &__tile-text {
    grid-area: text;
    @extend %tile-gray-text;
  }

  &__tile-text2 {
    grid-area: text2;
    @extend %tile-gray-text;
  }

  &__tile-fill {
    grid-area: fil;
    @extend %tile-purple;
  }

  &__tile-fill2 {
    grid-area: fil2;
    @extend %tile-purple;
  }

  &__tile-fill3 {
    grid-area: fil3;
    @extend %tile-purple;
  }
}
</style>
