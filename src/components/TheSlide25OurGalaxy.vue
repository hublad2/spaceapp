<template>
  <section class="slide">
    <div class="slide__star-hero">
      <h1>Galaktyka</h1>
    </div>
    <div class="slide__caption">
      <h2>Droga mleczna</h2>
    </div>
    <div class="slide__caption2">
      <h3>Położenie Ziemi w Drodze Mlecznej</h3>
    </div>
    <div class="slide__caption3">
      <h4>Droga Mleczna widziana z Ziemi</h4>
    </div>
    <div class="slide__image">
      <img src="../assets/ESO_-_Milky_Way.jpg" alt="Droga Mleczna" />
    </div>
    <div class="slide__image2">
      <img
        src="../assets/1024px-Galactic_longitude.jpg"
        alt="Położenie Ziemi w Drodze Mlecznej"
      />
    </div>
    <div class="slide__image3">
      <img
        src="../assets/1280px-ESO-VLT-Laser-phot-33a-07.jpg"
        alt="Droga Mleczna widziana z Ziemi"
      />
    </div>
    <div class="slide__tile-text">
      <p>
        Układ Słoneczny jest częścią galaktyki Drogi Mlecznej. Galaktyka ma
        średnicę około 100 000 lat świetlnych i zawiera od 100 do 400 miliardów
        gwiazd. W jej centrum znajduje się supermasywna czarna dziura o masie
        4,3 milionów mas Słońc. Naszą galaktykę można zobaczyć gołym okiem na
        nocnym niebie. Przez swój spiralny, wypłaszczony kształt, przypomina
        jasną smugę opasającą niebo.
      </p>
    </div>
    <div class="slide__tile-text2">
      <p>
        Istnienie supermasywnej czarnej dziury w centrum Drogi Mlecznej zostało
        potwierdzone na podstawie obserwacji przeprowadzonych w latach
        1992-2002.
      </p>
    </div>
    <div class="slide__tile-fill"></div>
  </section>
</template>

<script>
export default {
  name: "TheSlide25OurGalaxy",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide {
  @extend %slide-settings;
  grid-template-rows: repeat(32, 16.6666vw);
  grid-template-areas:
    "hero hero hero hero hero hero   "
    "hero hero hero hero hero hero   "
    ".    .    .    .    .    .   "
    "cap cap cap    .  .  . "
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "fil    text text text text text"
    "fil  text text text text text"
    "fil  text text text text text"
    ".  text text text text text"
    ".  text text text text text"
    ".  text text text text text"
    ".      .     .   .   .   ."
    "text2  text2 text2 text2 text2 ."
    "text2  text2 text2 text2 text2 ."
    "text2  text2 text2 text2 text2 ."
    "text2  text2 text2 text2 text2 ."
    ".    .    .    .    .    .   "
    ". . .    cap2  cap2  cap2 "
    "img2  img2  img2  img2  img2  img2"
    "img2  img2  img2  img2  img2  img2"
    "img2  img2  img2  img2  img2  img2"
    "img2  img2  img2  img2  img2  img2"
    ".    .    .    .    .    .   "
    "cap3 cap3 cap3    .  .  . "
    "img3  img3  img3  img3  img3  img3"
    "img3  img3  img3  img3  img3  img3"
    "img3  img3  img3  img3  img3  img3"
    "img3  img3  img3  img3  img3  img3"
    ".    .    .    .    .    .   ";

  @media screen and (min-width: 700px) {
    grid-template-rows: repeat(28, 6.5vw);
    grid-template-areas:
      "hero  hero  hero  hero hero hero hero hero   hero  hero "
      "hero  hero  hero  hero hero hero hero hero   hero  hero "
      ".     .     .     .    .    .    .     .     .     .    "
      "cap   cap   cap   cap  .    .    .     .     .     .    "
      "img   img   img   img  img  img  img   img   img   img  "
      "img   img   img   img  img  img  img   img   img   img  "
      "img   img   img   img  img  img  img   img   img   img  "
      "img   img   img   img  img  img  img   img   img   img  "
      "img   img   img   img  img  img  img   img   img   img  "
      "text  text  text  text text text text text2 text2 text2 "
      "text  text  text  text text text text text2 text2 text2 "
      "text  text  text  text text text text text2 text2 text2 "
      "fil   fil   fil   .    .    .    .    text2 text2 text2 "
      ".     .     .     .    .    .    .     .     .     .    "
      ".     .     .     .    .    .    cap2  cap2  cap2  cap2 "
      "img2  img2  img2  img2 img2 img2 img2  img2  img2  img2 "
      "img2  img2  img2  img2 img2 img2 img2  img2  img2  img2 "
      "img2  img2  img2  img2 img2 img2 img2  img2  img2  img2 "
      "img2  img2  img2  img2 img2 img2 img2  img2  img2  img2 "
      "img2  img2  img2  img2 img2 img2 img2  img2  img2  img2 "
      ".     .     .     .    .    .    .     .     .     .    "
      "cap3  cap3  cap3  cap3 .    .    .     .     .     .    "
      "img3  img3  img3  img3 img3 img3 img3  img3  img3  img3 "
      "img3  img3  img3  img3 img3 img3 img3  img3  img3  img3 "
      "img3  img3  img3  img3 img3 img3 img3  img3  img3  img3 "
      "img3  img3  img3  img3 img3 img3 img3  img3  img3  img3 "
      "img3  img3  img3  img3 img3 img3 img3  img3  img3  img3 "
      ".     .     .     .    .    .    .     .     .     .    ";
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
    @extend %tile-white;
    /* @extend %tile-purple; */
  }

  &__caption2 {
    grid-area: cap2;
    @extend %tile-white;
    /* @extend %tile-purple; */
    @media screen and (min-width: 700px) {
      font-size: 2vw;
    }
  }

  &__caption3 {
    grid-area: cap3;
    @extend %tile-white;
    /* @extend %tile-purple; */
    @media screen and (min-width: 700px) {
      font-size: 2vw;
    }
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

  &__image2 {
    grid-area: img2;
    display: flex;
    justify-content: center;
    align-items: center;

    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  &__image3 {
    grid-area: img3;
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
    text-align: center;
    @extend %tile-purple-text;
  }
}
</style>
