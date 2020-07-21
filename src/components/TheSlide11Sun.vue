<template>
  <div>
    <section class="slide">
      <div class="slide__star-hero">
        <h1>Obiekty układu</h1>
      </div>
      <div class="slide__caption">
        <h2>Słońce</h2>
      </div>
      <div class="slide__image">
        <img
          src="../assets/1024px-Solar_prominence_from_STEREO_spacecraft_September_29,_2008.jpg"
          alt="Betelgeza"
        />
      </div>
      <div class="slide__tile-text">
        <p>
          Słońce to największy obiekt w układzie słonecznym. To gwiazda średnich
          rozmiarów i masy.
          <br />
          <br />
          Masa: 1,98855 x 10³⁰ kg
          <br />
          <br />
          Promień: 696 342 km (109 promieni Ziemi)
        </p>
      </div>
      <div v-if="!loaded" class="slide__button">
        <button @click="engage">Więcej zdjęć</button>
      </div>
    </section>
    <div v-if="results && loaded">
      <TheSlide11Fetch
        v-for="(item, index) in results"
        :item="item"
        :index="index + 1"
        :key="item.data[0].nasa_id"
        :id="`sun-pic${index}`"
      />
    </div>
    <TheButton @click="pushImages" v-if="loaded" />
  </div>
</template>

<script>
import TheSlide11Fetch from "@/components/TheSlide11Fetch.vue";
import TheButton from "@/components/TheButton.vue";

export default {
  name: "TheSlide11Sun",
  components: {
    TheSlide11Fetch,
    TheButton,
  },
  data() {
    return {
      results: [],
      superResults: [],
      loaded: false,
      currentPic: 9,
    };
  },
  methods: {
    engage() {
      this.loaded = true;
      this.fetchImages();
    },
    async fetchImages() {
      const API = "https://images-api.nasa.gov/search?q=Sun";

      let response = await fetch(`${API}&media_type=image`);
      let jsonResponse = await response.json();
      this.superResults = jsonResponse.collection.items;

      this.pushImages(this.currentPic, this.superResults);
    },
    async pushImages() {
      let positionY = window.scrollY;
      this.results = this.superResults.slice(0, this.currentPic);
      if (this.currentPic == 9) {
        await this.$nextTick();
        document.querySelector("#sun-pic0").scrollIntoView({
          behavior: "smooth",
        });
      } else {
        await this.$nextTick();
        window.scroll(window.scrollX, positionY);
        document
          .querySelector(`#sun-pic${this.currentPic - 10}`)
          .scrollIntoView({
            behavior: "smooth",
          });
      }
      this.currentPic += 10;
    },
  },
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
    "hero hero hero hero hero .     "
    "hero hero hero hero hero .     "
    ".    .    .    .    .    .     "
    ".    .    .    cap  cap  cap   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "text text text text text text  "
    "text text text text text text  "
    "text text text text text text  "
    "text text text text text text  "
    ".    .    .    .    .    .     "
    ".    but  but  but  but  .     "
    ".    .    .    .    .    .     ";

  &__star-hero {
    grid-area: hero;
    @extend %tile-gray-header;
    /* @extend %tile-white-header; */
    /*  @extend %tile-white; */
    /* @extend %tile-gray; */
    font-size: 8vw;
  }

  &__caption {
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

  &__tile-text {
    grid-area: text;
    @extend %tile-gray-text;
  }

  &__button {
    grid-area: but;

    button {
      width: 100%;
      height: 100%;
      @extend %button;
      font-size: 5vw;
    }
  }

  &__tile-text2 {
    grid-area: text2;
    @extend %tile-gray-text;
  }
}
</style>
