<template>
  <section class="slide">
    <div class="slide__tile-bang">
      <h2>Po wielkim wybuchu</h2>
    </div>
    <div class="slide__tile-time">
      <h1>1 miliard - 13.8 miliarda lat (obecnie)</h1>
    </div>
    <div class="slide__tile-caption">
      <h3>Gromada Abell'a</h3>
    </div>
    <div class="slide__image">
      <img src="../assets/800px-Abell_S740.jpg" alt="Zdjęcie galaktyk" />
    </div>
    <div class="slide__tile-fill"></div>
    <div class="slide__tile-text">
      <p>
        Miliard lat po wielkim wybuchu, wszechświat wyglądał bardzo podobnie do
        tego jaki obserwujemy obecnie. Gwiazdy formowały się i umierały,
        wytwarzając w trakcie cięższe pierwiastki, a galaktyki w wyniku
        działania sił grawitacji były ku sobie przyciągane tworząć gromady i
        supegromady. I w ten sposób dochodzimy do 13.8 miliarda lat po wielkim
        wybuchu, czyli szacowanego obecnie wieku wszechświata.
      </p>
    </div>
    <div class="slide__tile-fill2"></div>
    <div class="slide__system-header">
      <h4>Układ słoneczny</h4>
    </div>
    <div class="slide__tile-text2">
      <p>
        Dotarliśmy do czasów obecnych więc warto przyjrzeć się naszej
        najbliższej okolicy - układowi słonecznemu. Jakie obiekty się w nim
        znajdują? Jak powstał? Jaki los go czeka?
      </p>
    </div>
  </section>
</template>

<script>
export default {
  name: "TheSlide9Now",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide {
  @extend %slide-settings;
  grid-template-rows: repeat(25, 16.6666vw);
  grid-template-areas:
    "time time time time time .   "
    "time time time time time .   "
    "time time time time time .   "
    ".    .    .    .    bang bang"
    "cap  cap  cap  .    bang bang"
    "img  img  img  img  img  img "
    "img  img  img  img  img  img "
    "img  img  img  img  img  img "
    "img  img  img  img  img  img "
    "img  img  img  img  img  img "
    "text text text text text .   "
    "text text text text text .   "
    "text text text text text fil "
    "text text text text text fil "
    "text text text text text fil "
    "text text text text text fil "
    "text text text text text fil "
    ".    .    .    .    .    .   "
    "header header header header header header"
    "header header header header header header"
    ".    .    .    .    .    .   "
    ".    text2 text2 text2 text2 text2 "
    ".    text2 text2 text2 text2 text2 "
    ".    text2 text2 text2 text2 text2 "
    ".    .    .    .    .    .   ";

  @media screen and (min-width: 700px) {
    grid-template-rows: repeat(15, 6.5vw);
    grid-template-areas:
      ".    .    .   .   .    time time time time time    "
      "cap  cap  cap cap .    time time time time time    "
      "img  img  img img img  img  bang bang bang  bang "
      "img  img  img img img  img  bang bang bang  bang "
      "img  img  img img img  img  bang bang bang  bang "
      "text text text text text text text text text text"
      "text text text text text text text text text text"
      "text text text text text text text text text text"
      ".    .    .    .    .    .   .   .   .   ."
      "header header header header header header header header header header"
      "header header header header header header header header header header"
      "fil    fil    fil    text2  text2  text2  text2  text2  text2  text2"
      ".    .    .    text2  text2  text2  text2  text2  text2  text2"
      ".    .    .    .    .    .   .   .   .   .";
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
    @extend %tile-white-header;
    /* @extend %tile-white; */

    @media screen and (max-width: 700px) {
      font-size: 7vw;
    }
  }

  &__tile-caption {
    grid-area: cap;
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

  &__tile-text {
    grid-area: text;
    @extend %tile-gray-text;
  }

  &__tile-fill2 {
    grid-area: fil2;
    @extend %tile-purple;
  }

  &__system-header {
    grid-area: header;
    @extend %tile-white-header;
  }

  &__tile-text2 {
    grid-area: text2;
    @extend %tile-gray-text;
  }
}
</style>
