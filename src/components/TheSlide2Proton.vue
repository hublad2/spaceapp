<template>
  <section class="slide">
    <div class="slide__tile-bang">
      <h2>Po wielkim wybuchu</h2>
    </div>
    <div class="slide__tile-time">
      <h1>10⁻⁶ s</h1>
    </div>
    <div class="slide__tile-caption">
      <h3>Neutron</h3>
    </div>
    <div class="slide__image">
      <img
        src="../assets/1024px-Quark_structure_neutron.svg.png"
        alt="Neutron"
      />
    </div>
    <div class="slide__tile-fill"></div>
    <div class="slide__tile-text">
      <p>
        Kwarki łączą się w protony, protony i elektrony tworzą neutrony. Materia
        i antymateria anihiluje. Pozostaje jedynie materia, która buduje
        wszechświat obecnie.
      </p>
    </div>
    <div class="slide__tile-fill2"></div>
  </section>
</template>

<script>
export default {
  name: "TheSlide2Proton",
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
    "bang bang bang bang time time"
    "bang bang bang bang time time"
    "bang bang bang bang .    .   "
    ".    .    .    .    .    .   "
    ".    .    .    cap  cap  cap "
    "img  img  img  img  img  img "
    "img  img  img  img  img  img "
    "img  img  img  img  img  img "
    "img  img  img  img  img  img "
    "text text text text text fil "
    "text text text text text fil "
    "text text text text text fil "
    "text text text text text fil "
    "fil2 fil2 fil2 fil2 .    .   "
    ".    .    .    .    .    .    ";

  @media screen and (min-width: 700px) {
    grid-template-rows: repeat(8, 6.5vw);
    grid-template-areas:
      "time time .    .    cap  cap  cap  cap  cap  .   "
      "time time .     .  img img img  img  img  img"
      "bang bang bang bang  img img img  img  img  img"
      "bang bang bang bang  img img img  img  img  img"
      "bang bang bang bang  img img img  img  img  img"
      ".   .   text text text text text  fil2  fil2    .   "
      ".   .   text text text text text fil2 fil2 .     "
      ".   .   .    .    .    .    .    .    .    .    ";
  }

  &__tile-time {
    grid-area: time;
    /* @extend %tile-gray-header; */
    /* @extend %tile-white-header; */
    /* @extend %tile-white; */
    @extend %tile-gray;
  }

  &__tile-bang {
    grid-area: bang;
    /* @extend %tile-gray-header; */
    @extend %tile-white-header;
    /* @extend %tile-white; */
    /* @extend %tile-gray; */
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
