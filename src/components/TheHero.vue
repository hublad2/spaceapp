<template>
  <div class="hero">
    <div class="hero-wrapper">
      <header class="hero__header">historia wszechświata</header>
      <h2 class="hero__header-second">Podróź od początku, aż do końca</h2>
      <button @click="moveToFirstSlide" class="hero__button">Rozpocznij</button>
    </div>
    <img
      class="hero__background"
      src="../assets/PngItem_1698962.png"
      alt="Nebula"
    />
  </div>
</template>

<script>
export default {
  name: "TheHero",
  methods: {
    moveToFirstSlide() {
      document.querySelector("#slide1").scrollIntoView({
        behavior: "smooth",
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.hero {
  height: 100vh;
  display: flex;
  align-items: center;
  padding: 0 5vw;
  z-index: 1;
  position: relative;
  overflow: hidden;

  &__header {
    font-family: "Montserrat", sans-serif;
    font-size: 3.6rem;
    text-transform: uppercase;
    color: white;

    @media screen and (min-width: 450px) {
      font-size: calc(3.6rem + 3vw);
    }
  }

  &__header-second {
    font-family: "Open Sans", sans-serif;
    font-size: 2rem;
    margin: 6vh 0 20vh 0;
    color: $colorFont3;
    font-weight: 600;

    @media screen and (min-width: 450px) {
      font-size: calc(2rem + 3vw);
    }
  }

  &__button {
    font-size: 2rem;
    width: calc(197px + 3vw);
    height: calc(57px + 2vw);
    z-index: 99;
    @extend %button;

    @media screen and (min-width: 450px) {
      font-size: calc(2rem + 0.7vw);
    }
  }

  &__background {
    position: absolute;
    width: 1000px;
    height: 1000px;
    left: -90%;
    top: -20%;
    opacity: 0.3;
    transform: rotate(180deg);
    z-index: 0;

    @media screen and (min-width: 450px) {
      left: -50%;
    }

    @media screen and (min-width: 750px) {
      left: -10%;
      right: 0;
      top: -30%;
      margin-left: auto;
      margin-right: auto;
      width: 170vh;
      height: 170vh;
      transform: rotate(50deg);
    }
  }
}

.hero-wrapper {
  z-index: 1;
}
</style>
