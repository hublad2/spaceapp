<template>
  <div>
    <section class="slide">
      <div class="slide__caption">
        <h2>Jowisz</h2>
      </div>
      <div class="slide__image">
        <img
          src="../assets/Jupiter_and_its_shrunken_Great_Red_Spot_(cropped).jpg"
          alt="Jowisz"
        />
      </div>
      <div class="slide__tile-text">
        <p>
          Jowisz jest gazowym olbrzymem, składa się głównie z wodoru i helu.
          Jego średnia gęstość wynosi 1,3 g/cm³, czyli nieco więcej od wody.
          Posiada silne pole magnetyczne, a na powierzchni szaleją wiatry
          osiągające prędkości nawet do 360 km/h.
          <br />
          <br />
          Masa: 1,89 × 10²⁷ kg (318 mas Ziemi)
          <br />
          <br />
          Promień: 71 492 km (11,2 promienii Ziemi)
          <br />
          <br />
          Średnia temperatura: -108° C
        </p>
      </div>
      <div class="slide__tile-text2">
        <p>
          Na Jowiszu, dzięki silnemu polu magnetycznemu, przy biegunach powstają
          zorze.
        </p>
      </div>
      <div class="slide__caption-aside">
        <h3>Jowisz - zorza</h3>
      </div>
      <div class="slide__image-aside">
        <img src="../assets/Jupiter.Aurora.HST.UV.jpg" alt="Jowisz - zorza" />
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
        :id="`jup-pic${index}`"
      />
    </div>
    <TheButton @click="pushImages" v-if="loaded" />
  </div>
</template>

<script>
import TheSlide11Fetch from "@/components/TheSlide11Fetch.vue";
import TheButton from "@/components/TheButton.vue";

export default {
  name: "TheSlide16Jupiter",
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
      const API = "https://images-api.nasa.gov/search?q=Jupiter";

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
        document.querySelector("#jup-pic0").scrollIntoView({
          behavior: "smooth",
        });
      } else {
        await this.$nextTick();
        window.scroll(window.scrollX, positionY);
        document
          .querySelector(`#jup-pic${this.currentPic - 10}`)
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
  grid-template-rows: repeat(24, 16.6666vw);
  grid-template-areas:
    ".    .    .    cap  cap  cap   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "text text text text text .  "
    "text text text text text .  "
    "text text text text text .  "
    "text text text text text .     "
    "text text text text text .     "
    "text text text text text .     "
    "text text text text text .     "
    ". . text2 text2 text2 text2     "
    ". . text2 text2 text2 text2     "
    ". . text2 text2 text2 text2     "
    ".    .    .    .    .    .     "
    "capa  capa  capa    .    .    .     "
    "imga  imga  imga  imga  imga  imga   "
    "imga  imga  imga  imga  imga  imga   "
    "imga  imga  imga  imga  imga  imga   "
    "imga  imga  imga  imga  imga  imga   "
    ".    .    .    .    .    .     "
    ".    but  but  but  but  .     "
    ".    .    .    .    .    .     ";

  @media screen and (min-width: 700px) {
    grid-template-rows: repeat(20, 6.5vw);
    grid-template-areas:
      ".    .    .   .   .    .    cap  cap  cap cap "
      "img  img  img img img  img  img  img  img img "
      "img  img  img img img  img  img  img  img img "
      "img  img  img img img  img  img  img  img img "
      "img  img  img img img  img  img  img  img img "
      "img  img  img img img  img  img  img  img img "
      "text text text text text text text text2 text2 text2"
      "text text text text text text text text2 text2 text2"
      "text text text text text text text text2 text2 text2"
      "text text text text text text text .     .     .    "
      ".    .    .    .    .    .    .    .    .    .   "
      "capa capa capa capa .    .    .    .    .    .   "
      "imga  imga  imga  imga imga   imga imga  imga  imga  imga "
      "imga  imga  imga  imga imga   imga imga  imga  imga  imga "
      "imga  imga  imga  imga imga   imga imga  imga  imga  imga "
      "imga  imga  imga  imga imga   imga imga  imga  imga  imga "
      "imga  imga  imga  imga imga   imga imga  imga  imga  imga "
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

  &__tile-text2 {
    grid-area: text2;
    @extend %tile-purple-text;
  }

  &__caption-aside {
    grid-area: capa;
    @extend %tile-purple;

    @media screen and (min-width: 700px) {
      font-size: 2vw;
    }
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
    }
  }
}
</style>
