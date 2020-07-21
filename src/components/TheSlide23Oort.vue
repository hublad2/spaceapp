<template>
  <section class="slide">
    <div class="slide__caption">
      <h2>Obłok Oorta</h2>
    </div>
    <div class="slide__caption2">
      <h3>300 - 100000 j.a.</h3>
    </div>
    <div class="slide__image">
      <img
        src="../assets/PIA17046_-_Voyager_1_Goes_Interstellar.jpg"
        alt="Obłok Oorta"
      />
    </div>
    <div class="slide__tile-text">
      <p>
        Hipotetyczny obłok, składający się z pyłu, drobnych okruchów i planetoid
        obiegających Słońce w odległości od 300 do 100 000 j.a. Składa się
        głównie z lodu i zestalonych gazów takich jak amoniak czy metan.
        Zewnętrzne granice Obłoku Oorta wyznaczają granicę dominacji
        grawitacyjnej Słońca, a tym samym granicę Układu Słonecznego.
      </p>
    </div>
    <div class="slide__tile-fill"></div>
  </section>
</template>

<script>
export default {
  name: "TheSlide23Oort",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide {
  @extend %slide-settings;
  grid-template-rows: repeat(13, 16.6666vw);
  grid-template-areas:
    "cap2 cap2 .    cap  cap  cap "
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
    ".      .  fil  fil  fil  fil"
    ".    .    .    .    .    .  ";

  &__caption {
    grid-area: cap;
    font-size: 5vw;
    /* @extend %tile-white; */
    @extend %tile-purple;
  }

  &__caption2 {
    grid-area: cap2;
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
}
</style>
