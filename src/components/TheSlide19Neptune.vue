<template>
  <div>
    <section class="slide">
      <div class="slide__caption">
        <h2>Neptun</h2>
      </div>
      <div class="slide__image">
        <img
          src="../assets/Neptune_-_Voyager_2_(29347980845)_flatten_crop.jpg"
          alt="Neptun"
        />
      </div>
      <div class="slide__tile-text">
        <p>
          Lodowy olbrzym, najdalsza od Słońca planeta w Układzie Słonecznym.
          Neptuna, od Urana odróżnia między innymi duża aktywność pogodowa.
          Wiatry na planecie osiągają prędkości do 2100 km/h.
          <br />
          <br />
          Masa: 1 × 10²⁶ kg (17,2 mas Ziemi)
          <br />
          <br />
          Promień: 24 622 km (3,85 promienii Ziemi)
          <br />
          <br />
          Średnia temperatura: -201° C
        </p>
      </div>
      <div class="slide__tile-fill"></div>
      <div class="slide__caption-aside">
        <h3>Chmury na Neptunie</h3>
      </div>
      <div class="slide__image-aside">
        <img src="../assets/chmury.png" alt="Chmury na Neptunie" />
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
        :id="`nep-pic${index}`"
      />
    </div>
    <TheButton @click="pushImages" v-if="loaded" />
  </div>
</template>

<script>
import TheSlide11Fetch from "@/components/TheSlide11Fetch.vue";
import TheButton from "@/components/TheButton.vue";

export default {
  name: "TheSlide18Uranus",
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
      const API = "https://images-api.nasa.gov/search?q=Neptune";

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
        document.querySelector("#nep-pic0").scrollIntoView({
          behavior: "smooth",
        });
      } else {
        await this.$nextTick();
        window.scroll(window.scrollX, positionY);
        document
          .querySelector(`#nep-pic${this.currentPic - 10}`)
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
  grid-template-rows: repeat(21, 16.6666vw);
  grid-template-areas:
    ".    .    .    cap  cap  cap   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "fil text text text text text  "
    "fil text text text text text  "
    "fil text text text text text  "
    "fil text text text text text  "
    ". text text text text text  "
    ". text text text text text  "
    ". text text text text text  "
    ".    .    .    .    .    .     "
    "capa  capa  capa    .    .    .     "
    "imga  imga  imga  imga  imga  imga   "
    "imga  imga  imga  imga  imga  imga   "
    "imga  imga  imga  imga  imga  imga   "
    "imga  imga  imga  imga  imga  imga   "
    ".    .    .    .    .    .     "
    ".    but  but  but  but  .     "
    ".    .    .    .    .    .     ";

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

  &__tile-fill {
    grid-area: fil;
    @extend %tile-purple;
  }

  &__caption-aside {
    grid-area: capa;
    font-size: 5vw;
    @extend %tile-purple;
  }

  &__image-aside {
    grid-area: imga;
    display: flex;
    justify-content: center;
    align-items: center;

    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
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
}
</style>
