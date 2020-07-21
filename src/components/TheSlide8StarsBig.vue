<template>
  <section class="slide">
    <div class="slide__star-hero">
      <h1>Gwiazdy masywne</h1>
    </div>
    <div class="slide__caption">
      <h2>Betelgeza</h2>
    </div>
    <div class="slide__image">
      <img
        src="../assets/Digitized_Sky_Survey_Image_of_Betelgeuse.jpg"
        alt="Betelgeza"
      />
    </div>
    <div class="slide__tile-text">
      <p>
        Gwiazda masywne, czyli przekraczające 10 mas, zachowują się podobnie do
        gwiazd o średniej masie, są w stanie “spalać” cięższe pierwiastki, i
        przy zmianie “paliwa” zwiększają średnicę. Inaczej zachowują się jednak
        tuż przed końcem. Tak masywne gwiazdy pod koniec ewolucji mogą zapaść
        się do gwiazdy neutronowej - bardzo gęstego obiektu składającego się
        głównie z neutronów - lub czarnej dziury. Gwiazdy te żyją najkrócej.
      </p>
    </div>
    <aside class="slide__tile-side">
      <p>
        Gwiazdy te żyją najkrócej, ich czas aktywności można liczyć w
        dziesiątkach i setkach milionów lat.
      </p>
    </aside>
  </section>
</template>

<script>
export default {
  name: "TheSlide8StarsBig",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide {
  @extend %slide-settings;
  grid-template-rows: repeat(20, 16.6666vw);
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
    "text text text text text .  "
    "text text text text text .  "
    "text text text text text .  "
    "text text text text text .  "
    "text text text text text .  "
    "text text text text text .  "
    "text text text text text .  "
    ".    .    .    .    .    .   "
    ".    .   aside aside aside aside"
    ".    .   aside aside aside aside"
    ".    .    .    .    .    .   ";

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

  &__tile-text {
    grid-area: text;
    @extend %tile-gray-text;
  }

  &__tile-side {
    grid-area: aside;
    @extend %tile-purple-text;
  }
}
</style>
