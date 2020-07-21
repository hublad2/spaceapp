<template>
  <div>
    <section class="slide">
      <div class="slide__caption">
        <h2>Wenus</h2>
      </div>
      <div class="slide__image">
        <img
          src="../assets/PIA23791-Venus-NewlyProcessedView-20200608.jpg"
          alt="Wenus"
        />
      </div>
      <div class="slide__tile-text">
        <p>
          Wenus jest drugą planetą w kolejności od Słońca. Jego powierzchnia -
          pokryta kraterami - bardzo przypomina powierzchnię księżyca, posiada
          rzadką atmosferę.
          <br />
          <br />
          Masa: 4,867 × 10²⁴ kg (0.815 masy Ziemi)
          <br />
          <br />
          Promień: 6052 km (0.95 promieni Ziemi)
        </p>
      </div>
      <div class="slide__tile-fill"></div>
      <div class="slide__tile-aside">
        <p>
          Atmosfera wenus w 95% składa się z dwutlenku węgla, co - przez efekt
          cieplarniany - powoduje wzrost temperatury na planecie do 464° C.
          Gdyby Wenus nie posiadała atmosfery jej średnia temperatura na
          powierzchni wynosiłaby -50° C.
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
        :id="`ven-pic${index}`"
      />
    </div>
    <TheButton @click="pushImages" v-if="loaded" />
  </div>
</template>

<script>
import TheSlide11Fetch from "@/components/TheSlide11Fetch.vue";
import TheButton from "@/components/TheButton.vue";

export default {
  name: "TheSlide13Venus",
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
      const API = "https://images-api.nasa.gov/search?q=Venus";

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
        document.querySelector("#ven-pic0").scrollIntoView({
          behavior: "smooth",
        });
      } else {
        await this.$nextTick();
        window.scroll(window.scrollX, positionY);
        document
          .querySelector(`#ven-pic${this.currentPic - 10}`)
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
  grid-template-rows: repeat(18, 16.6666vw);
  grid-template-areas:
    ".    .    .    cap  cap  cap   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "text text text text text fill  "
    "text text text text text fill  "
    "text text text text text fill  "
    "text text text text text .     "
    "text text text text text .     "
    "text text text text text .     "
    ".    asid asid asid asid asid  "
    ".    asid asid asid asid asid  "
    ".    asid asid asid asid asid  "
    ".    asid asid asid asid asid  "
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
    grid-area: fill;
    @extend %tile-purple;
  }

  &__tile-aside {
    grid-area: asid;
    @extend %tile-purple-text;
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
