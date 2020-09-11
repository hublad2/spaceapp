<template>
  <div>
    <section class="slide">
      <div class="slide__caption">
        <h2>Saturn</h2>
      </div>
      <div class="slide__image">
        <img src="../assets/1920px-Saturn_during_Equinox.jpg" alt="Saturn" />
      </div>
      <div class="slide__tile-text">
        <p>
          Saturn to kolejny gazowy olbrzym. Posiada ponad 50 księżyców.
          Największy z nich - Tytan, jest większy od Merkurego. Znany ze swoich
          9 pierścienii, składających się z lodu, skał i pyłu kosmicznego.
          <br />
          <br />
          Masa: 5,7 × 10²⁶ kg (95 mas Ziemi)
          <br />
          <br />
          Promień: 60 268 km (9,5 promienii Ziemi)
          <br />
          <br />
          Średnia temperatura: -139° C
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
        :id="`sat-pic${index}`"
      />
    </div>
    <TheButton @click="pushImages" v-if="loaded" />
  </div>
</template>

<script>
import TheSlide11Fetch from "@/components/TheSlide11Fetch.vue";
import TheButton from "@/components/TheButton.vue";

export default {
  name: "TheSlide17Saturn",
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
      const API = "https://images-api.nasa.gov/search?q=Saturn";

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
        document.querySelector("#sat-pic0").scrollIntoView({
          behavior: "smooth",
        });
      } else {
        await this.$nextTick();
        window.scroll(window.scrollX, positionY);
        document
          .querySelector(`#sat-pic${this.currentPic - 10}`)
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
  grid-template-rows: repeat(14, 16.6666vw);
  grid-template-areas:
    ".    .    .    cap  cap  cap   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "text text text text text text  "
    "text text text text text text  "
    "text text text text text text  "
    "text text text text text text  "
    "text text text text text text  "
    "text text text text text text  "
    ".    .    .    .    .    .     "
    ".    but  but  but  but  .     "
    ".    .    .    .    .    .     ";

  @media screen and (min-width: 700px) {
    grid-template-rows: repeat(13, 6.5vw);
    grid-template-areas:
      ".    .    .   .   .    .    cap  cap  cap cap "
      "img  img  img img img  img  img  img  img img "
      "img  img  img img img  img  img  img  img img "
      "img  img  img img img  img  img  img  img img "
      "img  img  img img img  img  img  img  img img "
      "img  img  img img img  img  img  img  img img "
      "text text text text text text text text text text"
      "text text text text text text text text text text"
      "text text text text text text text text text text"
      "text text text text text text text text text text"
      ".    .    .    .    .    .    .    .    .    .   "
      ".    .    .    but  but  but  but  .    .    .   "
      ".    .    .    .    .    .    .    .    .    .   ";
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
    }
  }
}
</style>
