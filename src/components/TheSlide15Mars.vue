<template>
  <div>
    <section class="slide">
      <div class="slide__caption">
        <h2>Mars</h2>
      </div>
      <div class="slide__image">
        <img src="../assets/1024px-Mars_Valles_Marineris.jpeg" alt="Mars" />
      </div>
      <div class="slide__tile-text">
        <p>
          Mars posiada rzadką atmosferę składającą się głównie z dwutlenku węgla
          i wody. W skład skorupy wchodzą między innymi krzem, związki żelaza
          czy siarka.
          <br />
          <br />
          Masa: 6,41 × 10²³ kg (0,1 masy Ziemi)
          <br />
          <br />
          Promień: 3390 km (0,5 promiena Ziemi)
          <br />
          <br />
          Średnia temperatura: -63° C
        </p>
      </div>
      <aside class="slide__tile-aside">
        <p v-if="!loadedWeather">
          Na marsie znajduje się obecnie łazik InSight, dzięki któremu wiemy
          jaka pogoda panuje na tej planecie.
        </p>
        <button @click="getWeather" v-if="!loadedWeather">
          Sprawdź pogodę
        </button>
        <h1 v-if="loadedWeather">Dzień solarny: {{ weather.solDay }}</h1>
        <p v-if="loadedWeather">
          Temperatura średnia: {{ weather.avgTemperature }}° C
          <br />
          Temperatura minimalna: {{ weather.minTemperature }}° C
          <br />
          Temperatura maksymalna: {{ weather.maxTemperature }}° C
          <br />
          Ciśnienie atmosferyczne: {{ weather.atmPressure }} hPa
          <br />
          Prędkość wiatru: {{ weather.wndSpeed }} m/s
          <br />
          Pora roku: {{ weather.season }}
        </p>
      </aside>
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
        :id="`mar-pic${index}`"
      />
    </div>
    <TheButton @click="pushImages" v-if="loaded" />
  </div>
</template>

<script>
import TheSlide11Fetch from "@/components/TheSlide11Fetch.vue";
import TheButton from "@/components/TheButton.vue";
import debounce from "lodash/debounce";

export default {
  name: "TheSlide15Mars",
  components: {
    TheSlide11Fetch,
    TheButton,
  },
  data() {
    return {
      results: [],
      superResults: [],
      loaded: false,
      loadedWeather: false,
      currentPic: 9,
      weather: {
        solDay: null,
        avgTemperature: null,
        minTemperature: null,
        maxTemperature: null,
        atmPressure: null,
        wndSpeed: null,
        season: null,
      },
    };
  },
  methods: {
    engage() {
      this.loaded = true;
      this.fetchImages();
    },
    async fetchImages() {
      const API = "https://images-api.nasa.gov/search?q=Mars";

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
        document.querySelector("#mar-pic0").scrollIntoView({
          behavior: "smooth",
        });
      } else {
        await this.$nextTick();
        window.scroll(window.scrollX, positionY);
        document
          .querySelector(`#mar-pic${this.currentPic - 10}`)
          .scrollIntoView({
            behavior: "smooth",
          });
      }
      this.currentPic += 10;
    },
    getWeather() {
      this.loadedWeather = true;
      this.fetchWeather();
    },
    fetchWeather: debounce(async function() {
      const API =
        "https://api.nasa.gov/insight_weather/?api_key=tQOlgZlTyisnCMawuh75wzIraZpWHsrE7mGDtDuZ&feedtype=json&ver=1.0";

      let response = await fetch(`${API}`);

      let responseJSON = await response.json();
      let { sol_keys } = responseJSON;

      const {
        AT: { av: avgTemp, mn: minTemp, mx: maxTemp },
        HWS: { av: avgWindSpeed },
        PRE: { av: avgAtmPressure },
        Season: season,
      } = responseJSON[sol_keys.pop()];

      this.weather.solDay = sol_keys.pop();
      this.weather.avgTemperature = Math.round((avgTemp - 32) / 1.8);
      this.weather.minTemperature = Math.round((minTemp - 32) / 1.8);
      this.weather.maxTemperature = Math.round((maxTemp - 32) / 1.8);
      this.weather.wndSpeed = Math.round(avgWindSpeed * 10) / 10;
      this.weather.atmPressure = Math.round(avgAtmPressure) / 100;
      this.weather.season = season;
    }, 500),
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide {
  @extend %slide-settings;
  grid-template-rows: repeat(20, 16.6666vw);
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
    "asid asid asid asid asid asid  "
    "asid asid asid asid asid asid  "
    "asid asid asid asid asid asid  "
    "asid asid asid asid asid asid  "
    "asid asid asid asid asid asid  "
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
      "text text text text text text asid asid asid asid"
      "text text text text text text asid asid asid asid"
      "text text text text text text asid asid asid asid"
      "text text text text text text   asid asid asid asid"
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

  &__tile-aside {
    grid-area: asid;
    @extend %tile-purple-text;

    flex-direction: column;
    text-align: center;

    padding: 5%;

    h1 {
      font-size: 9vw;
      margin-bottom: 13%;

      @media screen and (min-width: 700px) {
        font-size: 2.5vw;
        margin-bottom: 10%;
      }
    }

    p {
      margin: 0;
      line-height: 7vw;

      @media screen and (min-width: 700px) {
        line-height: 2.2vw;
        margin: 0 2%;
        font-size: 1.42vw;
      }
    }

    button {
      @extend %button;
      width: 90%;
      height: 25%;
      margin-top: 12%;
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
