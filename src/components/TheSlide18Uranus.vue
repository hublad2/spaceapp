<template>
  <div>
    <section class="slide">
      <div class="slide__caption">
        <h2>Uran</h2>
      </div>
      <div class="slide__image">
        <img src="../assets/Uranus2.jpg" alt="Uran" />
      </div>
      <div class="slide__tile-text">
        <p>
          Uran to planeta zewnętrzna. Podobnie jak Saturn posiada pierścienie i
          ponad 20 księżyców. Okrąża Słońce w ciągu 84 lat. Jego oś obrotu jest
          przechylona o ponad 90° w stosunku do płaszczyzny układu Słonecznego,
          co sprawia że po jednej stronie planety Słońce nie zachodzi przez 42
          lata, a po drugiej nie wschodzi przez taki sam czas.
          <br />
          <br />
          Masa: 8,7 × 10²⁵ kg (14,5 mas Ziemi)
          <br />
          <br />
          Promień: 25 362 km (4 promienie Ziemi)
          <br />
          <br />
          Średnia temperatura: -197° C
        </p>
      </div>
      <div class="slide__tile-fill"></div>
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
        :id="`ura-pic${index}`"
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
      const API = "https://images-api.nasa.gov/search?q=Uranus";

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
        document.querySelector("#ura-pic0").scrollIntoView({
          behavior: "smooth",
        });
      } else {
        await this.$nextTick();
        window.scroll(window.scrollX, positionY);
        document
          .querySelector(`#ura-pic${this.currentPic - 10}`)
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
  grid-template-rows: repeat(16, 16.6666vw);
  grid-template-areas:
    ".    .    .    cap  cap  cap   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "text text text text text fil  "
    "text text text text text fil  "
    "text text text text text fil  "
    "text text text text text fil  "
    "text text text text text fil  "
    "text text text text text .  "
    "text text text text text .  "
    "text text text text text .  "
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
