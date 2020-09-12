<template>
  <section class="slide">
    <div class="slide__star-hero">
      <h1>Prawo Hubble’a</h1>
    </div>
    <div class="slide__tile-text">
      <p>
        Odkryte w 1929 roku, przez Edwina Hubble’a opisuje zależność prędkości
        oddalania się galaktyk od odległości w jakiej się znajdują. Z obserwacji
        wynika, że światło innych galaktyk, spoza Grupy Lokalnej, jest
        przesunięte ku czerwieni, co zgodnie z prawem Dopplera, sugeruje że inne
        galaktyki oddalają się od Drogi Mlecznej. Jest to spowodowane jednak nie
        własną prędkością owych galaktyk, ale samego tempa rozszerzania się
        Wszechświata.
      </p>
    </div>
    <div class="slide__tile-text2">
      <h2>Prawo Hubble’a:</h2>
      <h3>v = Hd</h3>
    </div>
  </section>
</template>

<script>
export default {
  name: "TheSlide28Hubble",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide {
  @extend %slide-settings;
  grid-template-rows: repeat(14, 16.6666vw);
  grid-template-areas:
    "hero hero hero hero hero  hero "
    "hero hero hero hero hero  hero "
    ".    .    .    .    .    .  "
    "text  text text text text text"
    "text  text text text text text"
    "text  text text text text text"
    "text  text text text text text  "
    "text  text text text text text  "
    "text  text text text text text  "
    ".    .    .    .    .    .   "
    "text2  text2 text2 text2 text2 text2"
    "text2  text2 text2 text2 text2 text2"
    "text2  text2 text2 text2 text2 text2"
    ".    .    .    .    .    .   ";

  @media screen and (min-width: 700px) {
    grid-template-rows: repeat(8, 6.5vw);
    grid-template-areas:
      "hero hero hero hero hero  hero hero hero hero hero "
      "hero hero hero hero hero  hero hero hero hero hero "
      ".    .    .    .    .    .    .    .    .    .   "
      "text text text text text text text  text text text"
      "text text text text text text text  text text text"
      "text text text text text text text  text text text"
      "text2 text2 text2 text2 text2 text2 text2  text2 text2 text2"
      ".    .    .    .    .    .    .    .    .    .   ";
  }

  &__star-hero {
    grid-area: hero;
    /* @extend %tile-gray-header; */
    @extend %tile-white-header;
    /*  @extend %tile-white; */
    /* @extend %tile-gray; */
  }

  &__tile-text {
    grid-area: text;
    @extend %tile-gray-text;
  }

  &__tile-text2 {
    grid-area: text2;
    @extend %tile-purple-text;
    flex-direction: column;
    @media screen and (min-width: 700px) {
      flex-direction: row;
    }

    h2 {
      font-size: 10vw;

      @media screen and (min-width: 700px) {
        font-size: 2vw;
      }
    }

    h3 {
      margin-top: 10%;
      font-size: 12vw;
      font-style: italic;
      font-weight: 600;

      @media screen and (min-width: 700px) {
        font-size: 2vw;
        margin: 0 0 0 1%;
      }
    }
  }
}
</style>
