<template>
  <section class="slide">
    <div class="slide__star-hero">
      <h1>Gwiazdy małomasywne</h1>
    </div>
    <div class="slide__caption">
      <h2>Czerwony karzeł</h2>
    </div>
    <div class="slide__image">
      <img
        src="../assets/1280px-RedDwarfNASA-hue-shifted.jpg"
        alt="Czerwony karzeł"
      />
    </div>
    <div class="slide__tile-text">
      <p>
        Gwiazda małomasywne - czyli takie, których masa nie przekracza 0.5 masy
        Słońca. Każda gwiazda na początek robi użytek z najpowszechniejszego
        pierwiastka - wodoru, “spalając” go uzyskuje ogromne ilości energii.
      </p>
    </div>
    <div class="slide__tile-text2">
      <p>
        W pewnym momencie jednak wodór się kończy i gwiazda musi sięgnąć po inne
        źródło paliwa - cięższe pierwiastki, niestety gwiazdy tej masy nie
        wytwarzają odpowiednich warunków do ich “spalenia”. Gwiazdy takie świecą
        przez bardzo długi czas, rzędu 10 bilionów lat przez co, to w jaki
        sposób zakończy się ich życie jest nie do końca jasny, ponieważ od
        początku wszechświata, żadna taka gwiazda się jeszcze nie wypaliła.
      </p>
    </div>
    <div class="slide__tile-fill"></div>
  </section>
</template>

<script>
export default {
  name: "TheSlide6StarsSmall",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide {
  @extend %slide-settings;
  grid-template-rows: repeat(22, 16.6666vw);
  grid-template-areas:
    "hero hero hero hero hero .   "
    "hero hero hero hero hero .   "
    "hero hero hero hero hero .   "
    ".    .    .    .    .    .   "
    ".    .    .    cap  cap  cap "
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    ".    text text text text text"
    "fil  text text text text text"
    "fil  text text text text text"
    "fil  text text text text text"
    "fil  .    .    .    .    .   "
    "fil  text2 text2 text2 text2 text2"
    "fil  text2 text2 text2 text2 text2"
    ".    text2 text2 text2 text2 text2"
    ".    text2 text2 text2 text2 text2"
    ".    text2 text2 text2 text2 text2"
    ".    text2 text2 text2 text2 text2"
    ".    text2 text2 text2 text2 text2"
    ".  .    .    .    .    .   ";

  &__star-hero {
    grid-area: hero;
    /* @extend %tile-gray-header; */
    @extend %tile-white-header;
    /*  @extend %tile-white; */
    /* @extend %tile-gray; */
  }

  &__caption {
    grid-area: cap;
    font-size: 5vw;
    /* @extend %tile-white; */
    @extend %tile-purple;
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

  &__tile-text {
    grid-area: text;
    @extend %tile-gray-text;
  }

  &__tile-text2 {
    grid-area: text2;
    @extend %tile-gray-text;
  }
}
</style>
