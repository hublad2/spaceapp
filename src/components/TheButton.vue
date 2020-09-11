<template>
  <div class="slide3">
    <div class="slide3__button">
      <button @click="sendEventMore">Więcej zdjęć</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TheButton",
  methods: {
    sendEventMore() {
      this.$emit("click");
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide3 {
  @extend %slide-settings;
  grid-template-rows: repeat(2, 16.6666vw);
  grid-template-areas:
    ".    but  but  but  but  .     "
    ".    .    .    .    .    .     ";

  @media screen and (min-width: 700px) {
    grid-template-rows: repeat(2, 6.5vw);
    grid-template-areas:
      ".    .    .   but but  but  but   .    .   .    "
      ".    .    .   .   .    .    .     .    .   .    ";
  }

  &__button {
    grid-area: but;

    button {
      width: 100%;
      height: 100%;
      @extend %button;
    }
  }
}
</style>
