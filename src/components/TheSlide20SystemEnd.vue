<template>
  <section class="slide">
    <div class="slide__star-hero">
      <h1>Koniec układu</h1>
    </div>
    <div class="slide__caption">
      <h2>Mgławica i biały karzeł</h2>
    </div>
    <div class="slide__image">
      <img src="../assets/1024px-NGC6543.jpg" alt="Mgławica i biały karzeł" />
    </div>
    <div class="slide__tile-text">
      <p>
        Za około 7,5 mld Słońce zacznie “spalać” pierwiastki cięższe od wodoru,
        zamieni się w czerwonego olbrzyma, zwiększając, prawdopodobnie, swój
        rozmiar do rozmiarów orbity Ziemi. Oczywiście w skutek czego,
        jakiekolwiek życie na Ziemi przestanie istnieć.
      </p>
    </div>
    <div class="slide__tile-text2">
      <p>
        Później Słońce zacznie odrzucać swoją otoczkę, tworząć mgławicę. Na
        koniec zmniejszy rozmiary i zmieni się w białego karła, tracąc znaczną
        ilość materii w trakcie, co mocno wpłynie na orbity obiektów w układzie
        słonecznym.
      </p>
    </div>
    <div class="slide__tile-fill"></div>
    <div class="slide__tile-fill2"></div>
    <div class="slide__tile-fill3"></div>
  </section>
</template>

<script>
export default {
  name: "TheSlide20SystemEnd",
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
    ".    text text text text text"
    ".  text text text text text"
    ".  text text text text text"
    "fil2  text text text text text"
    "fil2  text text text text text"
    "fil  fil    fil    fil    fil    fil   "
    "text2  text2 text2 text2 text2 fil3"
    "text2  text2 text2 text2 text2 fil3"
    "text2  text2 text2 text2 text2 ."
    "text2  text2 text2 text2 text2 ."
    ".      .     .   .   .   .";

  @media screen and (min-width: 700px) {
    grid-template-rows: repeat(15, 6.5vw);
    grid-template-areas:
      "hero hero hero hero hero  hero hero hero hero hero "
      "hero hero hero hero hero  hero hero hero hero hero "
      ".    .    .    .    .    .    .    .    .    .   "
      ".     .     .     .     .     .     cap   cap   cap   cap "
      "img   img   img   img   img   img   img   img   img   img "
      "img   img   img   img   img   img   img   img   img   img "
      "img   img   img   img   img   img   img   img   img   img "
      "img   img   img   img   img   img   img   img   img   img "
      "img   img   img   img   img   img   img   img   img   img "
      ".     text  text  text  text  text  text  text  text  text"
      "fil2  text  text  text  text  text  text  text  text  text"
      "fil   fil   fil   fil   fil   fil   fil   fil   fil   fil "
      "text2 text2 text2 text2 text2 text2 text2 text2 text2 fil3"
      "text2 text2 text2 text2 text2 text2 text2 text2 text2 .   "
      ".     .     .     .     .     .     .     .     .     .   ";
  }

  &__star-hero {
    grid-area: hero;
    @extend %tile-gray-header;
    /* @extend %tile-white-header; */
    /*  @extend %tile-white; */
    /* @extend %tile-gray; */
  }

  &__caption {
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

  &__tile-fill2 {
    grid-area: fil2;
    @extend %tile-purple;
  }

  &__tile-fill3 {
    grid-area: fil3;
    @extend %tile-purple;
  }

  &__tile-text {
    grid-area: text;
    @extend %tile-gray-text;
  }

  &__tile-text2 {
    grid-area: text2;
    @extend %tile-gray-text;
  }
}
</style>
