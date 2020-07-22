<template>
  <section class="slide" id="slide1">
    <div class="slide__tile-time">
      <h1>10⁻⁴³ s</h1>
    </div>
    <div class="slide__tile-bang">
      <h2>Po wielkim wybuchu</h2>
    </div>
    <div class="slide__tile-caption">
      <h3>Promieniowanie reliktowe</h3>
    </div>
    <div class="slide__image">
      <img src="../assets/Ilc_9yr_moll4096.png" alt="Background radiation" />
    </div>
    <div class="slide__tile-fill"></div>
    <div class="slide__tile-text">
      <p>
        Dosłownie przed chwilą, narodziły się czas, przestrzeń i energia.
        Temperatura wszechświata jest ogromna, blisko 10³² °C, a jego rozmiar
        jest mniejszy od atomu. Wszystkie cztery oddziaływania: grawitacja,
        elektromagnetyzm, oddziaływania jądrowe silne i słabe, są zunifikowane.
      </p>
    </div>
    <div class="slide__tile-fill2"></div>
  </section>
</template>

<script>
export default {
  name: "TheSlide1Relic",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide {
  @extend %slide-settings;
  grid-template-rows: repeat(16, 16.6666vw);
  grid-template-areas:
    "time time bang bang bang bang"
    "time time bang bang bang bang"
    ".    .    bang bang bang bang"
    ".    .    .    .    .    .   "
    "cap  cap  cap  .    .    .   "
    "img  img  img  img  img  img "
    "img  img  img  img  img  img "
    "img  img  img  img  img  img "
    "img  img  img  img  img  img "
    "fil  text  text text text text"
    "fil  text  text text text text"
    ".    text text text text text"
    ".    text text text text text"
    ".    text text text text text"
    ".    .    .    .    fil2 fil2"
    ".    .    .    .    .    .   ";

  @media screen and (min-width: 700px) {
    grid-template-rows: repeat(10, 6.5vw);
    grid-template-areas:
      "cap cap cap  cap  cap  .    .    .    time time"
      "img img img  img  img  img  fil  fil  time time"
      "img img img  img  img  img  bang bang bang bang"
      "img img img  img  img  img  bang bang bang bang"
      "img img img  img  img  img  bang bang bang bang"
      ".   .   text text text text .    .    .    .   "
      ".   .   text text text text fil2 fil2 fil2 fil2"
      ".   .   text text text text fil2 fil2 fil2 fil2"
      ".   .   text text text text .    .    .    .   "
      ".   .   .    .    .    .    .    .    .    .    ";
  }

  &__tile-time {
    grid-area: time;
    @extend %tile-white-time;
  }

  &__tile-bang {
    grid-area: bang;
    @extend %tile-gray-header;
  }

  &__tile-caption {
    grid-area: cap;
    @extend %tile-white;
  }

  &__image {
    grid-area: img;
    display: flex;
    justify-content: center;
    align-items: center;

    img {
      width: 80%;
      height: 100%;
      object-fit: contain;
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

  &__tile-fill2 {
    grid-area: fil2;
    @extend %tile-purple;
  }
}
</style>
