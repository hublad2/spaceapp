<template>
  <section class="slide">
    <div class="slide__star-hero">
      <h1>Co dalej?</h1>
    </div>
    <div class="slide__tile-text">
      <p>
        W tym momencie możesz zdecydować, jaki temat chcesz kontynuować.
        <br />
        <br />
        Kliknij w interesujący Cię temat, do reszty będziesz mógł wrócić.
      </p>
    </div>
    <div class="slide__button">
      <button>Przyszłość wszechświata</button>
    </div>
    <div class="slide__button2">
      <button>Gwiazdy i pierwiastki</button>
    </div>
    <div class="slide__button3">
      <button>Czarne dziury</button>
    </div>
  </section>
</template>

<script>
export default {
  name: "TheSlide29End",
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
    "text  text text text text ."
    "text  text text text text ."
    "text  text text text text ."
    "text  text text text text .  "
    ".    .    .    .    .    .   "
    ".  but but but but ."
    ".    .    .    .    .    .   "
    ".  but2 but2 but2 but2 ."
    ".    .    .    .    .    .   "
    ".  but3 but3 but3 but3 ."
    ".    .    .    .    .    .   ";

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

  &__button {
    grid-area: but;

    button {
      width: 100%;
      height: 100%;
      @extend %button;
      font-size: 5vw;
    }
  }

  &__button2 {
    grid-area: but2;

    button {
      width: 100%;
      height: 100%;
      @extend %button;
      font-size: 5vw;
    }
  }

  &__button3 {
    grid-area: but3;

    button {
      width: 100%;
      height: 100%;
      @extend %button;
      font-size: 5vw;
    }
  }
}
</style>
