<template>
  <section class="slide">
    <div class="slide__tile-bang">
      <h2>Po wielkim wybuchu</h2>
    </div>
    <div class="slide__tile-time">
      <h1>370,000 lat - 150 milionów lat</h1>
    </div>
    <div class="slide__tile-caption">
      <h3>"Ciemna era"</h3>
    </div>
    <div class="slide__image">
      <img src="../assets/220px-Nucleus_drawing.svg.png" alt="Neutron" />
    </div>
    <div class="slide__tile-fill"></div>
    <div class="slide__tile-text">
      <p>
        Okres ten jest czasem nazywany “ciemną erą” wszechświata, ze względu na
        znikomą ilość promieniowania widzialnego. Gdyby przenieść kogoś w ten
        okres, zobaczyłby kompletną ciemność. Co nie oznacza, że nic się nie
        dzieje. Temperatura maleje w tym okresie, z około 4000° C do -200°C.
        Materia zaczyna się skupiać, co później pozwoli na zrodzenie się
        obiektów, które zapewniły nam między innymi - tlen. Nie, na plankton
        będziemy musieli jeszcze trochę poczekać, ale gwiazdy pojawią się już za
        chwile.
      </p>
    </div>
    <div class="slide__tile-fill2"></div>
  </section>
</template>

<script>
export default {
  name: "TheSlide1-Relic",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide {
  @extend %slide-settings;
  grid-template-rows: repeat(15, 16.6666vw);
  grid-template-areas:
    "time time time time time .    "
    "time time time time time .    "
    "time time time time time .    "
    ".    .    .    bang bang bang       "
    "cap  cap  cap  bang  bang bang       "
    "text text text text text .   "
    "text text text text text .   "
    "text text text text text .   "
    "text text text text text fil "
    "text text text text text fil "
    "text text text text text fil "
    "text text text text text fil "
    "text text text text text fil "
    "fil2 fil2 .    .    .    .   "
    ".    .    .    .    .    .  ";

  @media screen and (min-width: 700px) {
    grid-template-rows: repeat(9, 6.5vw);
    grid-template-areas:
      "time time time  time  time  .     .    .    .    .   "
      "time time time  time  time  cap   cap  cap  cap  cap "
      "bang bang bang  bang  bang  text  text text text text"
      "bang bang bang  bang  bang  text  text text text text"
      "bang bang bang  bang  bang  text  text text text text"
      ".    .    .     .     .     text  text text text text"
      "fil  fil  fil   .     .     text  text text text text"
      "fil  fil  fil   .     .     text  text text text text"
      ".    .    .     .     .     .     .    .    .    .   ";
  }

  &__tile-time {
    grid-area: time;
    /* @extend %tile-gray-header; */
    /* @extend %tile-white-header; */
    /*  @extend %tile-white; */
    @extend %tile-gray;
  }

  &__tile-bang {
    grid-area: bang;
    /* @extend %tile-gray-header; */
    @extend %tile-white-header;
    /* @extend %tile-white; */

    @media screen and (max-width: 700px) {
      font-size: 7vw;
    }
  }

  &__tile-caption {
    grid-area: cap;
    /* @extend %tile-white; */
    @extend %tile-purple;
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
