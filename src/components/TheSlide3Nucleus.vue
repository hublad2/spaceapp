<template>
  <section class="slide">
    <div class="slide__tile-bang">
      <h2>Po wielkim wybuchu</h2>
    </div>
    <div class="slide__tile-time">
      <h1>1 s - 370,000 lat</h1>
    </div>
    <div class="slide__tile-caption">
      <h3>Jądro atomowe</h3>
    </div>
    <div class="slide__image">
      <img src="../assets/220px-Nucleus_drawing.svg.png" alt="Neutron" />
    </div>
    <div class="slide__tile-fill"></div>
    <div class="slide__tile-text">
      <p>
        Powstają pierwsze jądra atomowe - takie jak jądro deuteru czy helu.
        Wszechświat stygnie. Powstałe jądra łączą się, tworząc coraz cięższe
        pierwiastki. Synteza kończy się na licie.
      </p>
    </div>
    <div class="slide__tile-fill2"></div>
  </section>
</template>

<script>
export default {
  name: "TheSlide3Nucleus",
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
    "time time bang bang bang bang"
    "time time bang bang bang bang"
    ".    .    bang bang bang bang"
    ".    .    .    .    .    .  "
    "cap  cap  cap  .    .    .  "
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "fil  text text text text text"
    "fil  text text text text text"
    "fil  text text text text text"
    "fil  text text text text text"
    ".    .    fil2 fil2 fil2 fil2"
    ".    .    .    .    .    .  ";

  &__tile-time {
    grid-area: time;
    /* @extend %tile-gray-header; */
    /* @extend %tile-white-header; */
    @extend %tile-white;
    /* @extend %tile-gray; */
  }

  &__tile-bang {
    grid-area: bang;
    @extend %tile-gray-header;
    /* @extend %tile-white-header; */
    /* @extend %tile-white; */
    /* @extend %tile-gray; */
  }

  &__tile-caption {
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
