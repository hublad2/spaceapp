<template>
  <section class="slide" id="beyond-neptune">
    <div class="slide__star-hero">
      <h1>Za Neptunem</h1>
    </div>
    <div class="slide__caption">
      <h2>Pas Kuipera</h2>
    </div>
    <div class="slide__caption2">
      <h3>30-50 j.a.</h3>
    </div>
    <div class="slide__image">
      <img
        src="../assets/1024px-Outersolarsystem_objectpositions_labels_comp.png"
        alt="Pas Kuipera"
      />
    </div>
    <div class="slide__tile-text">
      <p>
        Znajduje się w odległości od 30 do 50 jednostek astronomicznych od
        Słońca, czyli do 50 razy dalej niż Ziemia. Krążą w nim głównie lodowe
        planetoidy, ale także planety karłowate jak Pluton, Haumea i Makemake.
      </p>
    </div>
    <div class="slide__tile-fill"></div>
    <div class="slide__tile-fill2"></div>
    <div class="slide__caption3">
      <h4>Pluton</h4>
    </div>
    <div class="slide__image2">
      <img
        src="../assets/1024px-Pluto_in_True_Color_-_High-Res.jpg"
        alt="Pluton"
      />
    </div>
  </section>
</template>

<script>
export default {
  name: "TheSlide21AfterNeptune",
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
    "cap2 cap2 .    cap  cap  cap "
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "text text text text text .  "
    "text text text text text .  "
    "text text text text text fil  "
    "text text text text text fil"
    ".      .     .   .   .   fil   "
    "cap3 cap3 cap3    .    .    .   "
    "img2  img2  img2  img2  img2  img2"
    "img2  img2  img2  img2  img2  img2"
    "img2  img2  img2  img2  img2  img2"
    "img2  img2  img2  img2  img2  img2"
    ".      .     .   .   .   .   ";

  @media screen and (min-width: 700px) {
    grid-template-rows: repeat(19, 6.5vw);
    grid-template-areas:
      "hero hero hero hero hero  hero hero hero hero hero "
      "hero hero hero hero hero  hero hero hero hero hero "
      ".    .    .    .    .    .    .    .    .    .   "
      "cap  cap  cap cap .    .    .    .    .   .   "
      "img  img  img img img  img  img  img  cap2 cap2 "
      "img  img  img img img  img  img  img  cap2 cap2 "
      "img  img  img img img  img  img  img  fil  .     "
      "img  img  img img img  img  img  img  fil  fil2  "
      "img  img  img img img  img  img  img  .    fil2  "
      "text text text text text text text text text text"
      "text text text text text text text text text text"
      ".    .    .    .    .    .    .    .    .    .   "
      "cap3 cap3 cap3 cap3 .    .    .    .    .    .   "
      "img2  img2  img2  img2 img2   img2 img2  img2  img2  img2 "
      "img2  img2  img2  img2 img2   img2 img2  img2  img2  img2 "
      "img2  img2  img2  img2 img2   img2 img2  img2  img2  img2 "
      "img2  img2  img2  img2 img2   img2 img2  img2  img2  img2 "
      "img2  img2  img2  img2 img2   img2 img2  img2  img2  img2 "
      ".    .    .    .    .    .    .    .    .    .   ";
  }

  &__star-hero {
    grid-area: hero;
    /*  @extend %tile-gray-header; */
    @extend %tile-white-header;
    /*  @extend %tile-white; */
    /* @extend %tile-gray; */
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
