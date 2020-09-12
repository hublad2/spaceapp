<template>
  <section class="slide">
    <div class="slide__star-hero">
      <h1>Gwiezdne sąsiedztwo układu</h1>
    </div>
    <div class="slide__caption">
      <h2>Alfa Centauri A</h2>
    </div>
    <div class="slide__caption2">
      <h2>4,4 lata świetlne</h2>
    </div>
    <div class="slide__image">
      <img
        src="../assets/The_bright_star_Alpha_Centauri_and_its_surroundings.jpg"
        alt="Alfa Centauri"
      />
    </div>
    <div class="slide__tile-text">
      <p>
        W układzie Alfa Centauri, znajdują się trzy gwiazdy: Alfa Centauri A i B
        oraz czerwony karzeł Proxima Centauri. Układ znajduje się 4,4 lata
        świetlne od Ziemi, co czyni go najbliższym sąsiadem Układu Słonecznego.
        Gwiazda Alfa Centauri A jest trzecią, pod względem jasności gwiazdą
        widoczną na nocnym niebie.
      </p>
    </div>
    <div class="slide__tile-fill"></div>
    <div class="slide__tile-fill2"></div>
  </section>
</template>

<script>
export default {
  name: "TheSlide24Neighbourhood",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide {
  @extend %slide-settings;
  grid-template-rows: repeat(16, 16.6666vw);
  grid-template-areas:
    "hero hero hero hero hero .   "
    "hero hero hero hero hero .   "
    "hero hero hero hero hero .   "
    ".    .    .    .    .    .   "
    "cap2 cap2 .    cap  cap  cap "
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    ".    text text text text text"
    ".  text text text text text"
    "fil  text text text text text"
    "fil  text text text text text"
    "fil  text text text text text"
    "fil      .     .   .   .   ."
    ".    .    .    .    .    .   ";

  @media screen and (min-width: 700px) {
    grid-template-rows: repeat(12, 6.5vw);
    grid-template-areas:
      "hero hero hero hero hero  hero hero hero hero hero "
      "hero hero hero hero hero  hero hero hero hero hero "
      ".    .    .    .    .    .    .    .    .    .   "
      "cap  cap  cap cap .    .    .    .    .   .   "
      "img  img  img img img  img  img  img  cap2 cap2 "
      "img  img  img img img  img  img  img  cap2 cap2 "
      "img  img  img img img  img  img  img  fil  .     "
      "img  img  img img img  img  img  img  fil  fil2  "
      "img  img  img img img  img  img  img  .    fil2  "
      "text text text text text text text text text text"
      "text text text text text text text text text text"
      ".    .    .    .    .    .    .    .    .    .   ";
  }

  &__star-hero {
    grid-area: hero;
    /* @extend %tile-gray-header; */
    @extend %tile-white-header;
    /*  @extend %tile-white; */
    /* @extend %tile-gray; */
  }

  &__caption {
    grid-area: cap;
    /*  @extend %tile-white; */
    @extend %tile-purple;
  }

  &__caption2 {
    grid-area: cap2;
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

  &__tile-fill {
    grid-area: fil;
    @extend %tile-purple;
  }

  &__tile-fill {
    grid-area: fil2;
    @extend %tile-purple;
  }

  &__tile-text {
    grid-area: text;
    @extend %tile-gray-text;
  }
}
</style>
