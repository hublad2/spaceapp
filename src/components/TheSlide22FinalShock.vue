<template>
  <section class="slide">
    <div class="slide__caption">
      <h2>Szok końcowy</h2>
    </div>
    <div class="slide__caption2">
      <h3>~95 j.a.</h3>
    </div>
    <div class="slide__image">
      <img src="../assets/1280px-Voyagery.jpg" alt="Szok końcowy" />
    </div>
    <div class="slide__tile-text">
      <p>
        Powierzchnia dookoła Układu Słonecznego, gdzie wiatr słoneczny spowalnia
        do prędkości poddźwiękowej. Sonda Voyager 1 przekroczyła szok końcowy w
        grudniu 2004 roku.
      </p>
    </div>
    <div class="slide__tile-fill"></div>
    <div class="slide__tile-fill2"></div>
  </section>
</template>

<script>
export default {
  name: "TheSlide22FinalShock",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide {
  @extend %slide-settings;
  grid-template-rows: repeat(10, 16.6666vw);
  grid-template-areas:
    "cap2 cap2 .    cap  cap  cap "
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "text text text text text .  "
    "text text text text text .  "
    "text text text text text .  "
    "text text text text text ."
    ".      .     .   .   .   .   ";

  @media screen and (min-width: 700px) {
    grid-template-rows: repeat(9, 6.5vw);
    grid-template-areas:
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

  &__caption {
    grid-area: cap;
    /* @extend %tile-white; */
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

  &__tile-fill2 {
    grid-area: fil2;
    @extend %tile-purple;
  }

  &__tile-text {
    grid-area: text;
    @extend %tile-gray-text;
  }
}
</style>
