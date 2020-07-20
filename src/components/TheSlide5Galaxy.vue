<template>
  <section class="slide">
    <div class="slide__tile-bang">
      <h2>Po wielkim wybuchu</h2>
    </div>
    <div class="slide__tile-time">
      <h1>150 milionów - 1 miliard lat</h1>
    </div>
    <div class="slide__tile-caption">
      <h3>Galaktyka NGC 1300</h3>
    </div>
    <div class="slide__image">
      <img
        src="../assets/Hubble2005-01-barred-spiral-galaxy-NGC1300.jpg"
        alt="Galaktyka NGC 1300"
      />
    </div>
    <div class="slide__tile-fill"></div>
    <div class="slide__tile-text">
      <p>
        W tym okresie formują się pierwsze galaktyki, pojawia się nieco światła
        - pierwszy raz od powstania wscechświata skupiony gaz “zapala się”
        tworząc gwiazdy. W wyniku supernowych, pojawiły się pierwiastki cięższe
        od litu.
      </p>
    </div>
    <div class="slide__tile-fill2"></div>
    <div class="slide__stars-header">
      <h4>Ewolucja gwiazd</h4>
    </div>
    <div class="slide__tile-text2">
      <p>
        Zatrzymajmy się na chwilę przy temacie gwiazd i spójrzmy jak może
        wyglądać życie i ostatecznie również, śmierć takiego obiektu.
      </p>
    </div>
    <div class="slide__tile-fill3"></div>
  </section>
</template>

<script>
export default {
  name: "TheSlide5Galaxy",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide {
  @extend %slide-settings;
  grid-template-rows: repeat(22, 16.6666vw);
  grid-template-areas:
    ".    time time time time time"
    ".    time time time time time"
    ".    time time time time time"
    "bang bang .    .    .    .  "
    "bang bang .    cap  cap  cap"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "img  img  img  img  img  img"
    "text  text text text text fil"
    "text  text text text text fil"
    "text  text text text text fil"
    "text  text text text text fil"
    ".    .     .    .    .    fil"
    "stars stars stars stars stars stars"
    "stars stars stars stars stars stars"
    "fil3     .     .     .     .     .     "
    "text2 text2 text2 text2 text2 .     "
    "text2 text2 text2 text2 text2 .     "
    "text2 text2 text2 text2 text2 .     "
    ".     .     .     fil2  fil2  fil2  "
    ".     .     .     .     .     .     ";

  &__tile-time {
    grid-area: time;
    /* @extend %tile-gray-header; */
    @extend %tile-white-header;
    /* @extend %tile-white; */
    /* @extend %tile-gray; */
  }

  &__tile-bang {
    grid-area: bang;
    /* @extend %tile-gray-header; */
    /* @extend %tile-white-header; */
    /* @extend %tile-white; */
    @extend %tile-gray;
    font-size: 5.3vw;
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
    @extend %tile-gray-text;
  }

  &__stars-header {
    grid-area: stars;
    @extend %tile-gray-header;
  }

  &__tile-fill2 {
    grid-area: fil2;
    @extend %tile-purple;
  }

  &__tile-fill3 {
    grid-area: fil3;
    @extend %tile-purple;
  }
}
</style>
