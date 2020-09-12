<template>
  <section class="slide">
    <div class="slide__star-hero">
      <h1>Grupa Lokalna Galaktyk</h1>
    </div>
    <div class="slide__caption">
      <h2>Grupa Lokalna</h2>
    </div>
    <div class="slide__image">
      <img src="../assets/Local_Group_pl.svg.png" alt="Grupa Lokalna" />
    </div>
    <div class="slide__tile-text">
      <p>
        Droga Mleczna należy do Grupy Lokalnej Galaktyk, czyli skupiska
        galaktyk, które połączone oddziaływaniem grawitacyjnym, podróżują przez
        kosmos jako całość. Grupa rozciąga się na obszarze 10 milionów lat
        świetlnych.
      </p>
    </div>
    <div class="slide__tile-text2">
      <p>
        Inne galaktyki należące do Grupy Lokalnej to między innymi: Galaktyka
        Andromedy i Galaktyka Trójkąta.
      </p>
    </div>
    <div class="slide__tile-fill"></div>
  </section>
</template>

<script>
export default {
  name: "TheSlide26Local",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide {
  @extend %slide-settings;
  grid-template-rows: repeat(17, 16.6666vw);
  grid-template-areas:
    "hero hero hero hero hero  .  "
    "hero hero hero hero hero  .  "
    ".    .    .    .    .    .  "
    ".    .    .    cap  cap  cap"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "text  text text text text fil"
    "text  text text text text fil"
    "text  text text text text fil"
    "text  text text text text .  "
    ".     .    .    .    .    .  "
    ".  . text2 text2 text2 text2"
    ".  . text2 text2 text2 text2"
    ".  . text2 text2 text2 text2"
    ".    .    .    .    .    .   ";

  @media screen and (min-width: 700px) {
    grid-template-rows: repeat(13, 6.5vw);
    grid-template-areas:
      "hero  hero  hero  hero hero hero hero hero   hero  hero "
      "hero  hero  hero  hero hero hero hero hero   hero  hero "
      ".     .     .     .    .    .    .     .     .     .    "
      ".     .     .     .    .    .    cap   cap   cap   cap  "
      "img   img   img   img  img  img  img   img   img   img  "
      "img   img   img   img  img  img  img   img   img   img  "
      "img   img   img   img  img  img  img   img   img   img  "
      "img   img   img   img  img  img  img   img   img   img  "
      "img   img   img   img  img  img  img   img   img   img  "
      "text2 text2 text2  text text text text text text text "
      "text2 text2 text2  text text text text text text text "
      "text2 text2 text2  text text text text text text text "
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
    text-align: center;
    @extend %tile-purple-text;
  }
}
</style>
