<template>
  <section class="slide">
    <div class="slide__star-hero">
      <h1>Supergromada Lokalna</h1>
    </div>
    <div class="slide__caption">
      <h2>Gromady w Supergromadzie Lokalnej</h2>
    </div>
    <div class="slide__image">
      <img
        src="../assets/Virgosupercluster_atlasoftheuniverse.gif"
        alt="Gromady w Supergromadzie Lokalnej"
      />
    </div>
    <div class="slide__tile-text">
      <p>
        Z kolei Grupa Lokalna Galaktyk jest częścią Supegromady Lokalnej,
        ogromnej struktury, zajmującej obszar 200 milionów lat świetlnych. Cała
        supegromada jest przyciągana przez olbrzymie skupisko gromad galaktyk
        znane jako Wielki Atraktor, który powoduje ruch galaktyk z Supegromady
        Lokalnej ku swemu centrum z prędkością 100-300 km/s.
      </p>
    </div>
    <div class="slide__tile-fill"></div>
  </section>
</template>

<script>
export default {
  name: "TheSlide27Supergroup",
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
    ". hero hero hero hero  hero "
    ". hero hero hero hero  hero "
    ".    .    .    .    .    .  "
    "cap   cap    cap    .  .  ."
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "fil  text text text text text"
    "fil  text text text text text"
    "fil  text text text text text"
    ".  text text text text text  "
    ".  text text text text text  "
    ".  text text text text text  "
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

  &__tile-fill {
    grid-area: fil;
    @extend %tile-purple;
  }

  &__tile-text {
    grid-area: text;
    @extend %tile-gray-text;
  }
}
</style>
