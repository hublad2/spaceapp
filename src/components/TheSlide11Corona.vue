<template>
  <section class="slide-corona">
    <div class="slide-corona__text">
      <p>
        Słońce co jakiś czas wyrzuca z siebie naładowane cząstki - takie jak
        protony czy elektrony. Te wyrzutu nazywamy
        <i>koronalnym wyrzutem masy</i>, docierający do Ziemi wyrzut może
        powodować zorze polarne a nawet uszkodzenia linii energetycznych.
      </p>
    </div>
    <aside class="slide-corona__aside">
      <p v-if="!loadedCorona">Koronalnych wyrzutów masy w ostatnim miesiącu</p>
      <p v-if="loadedCorona">
        Koronalnych wyrzutów masy w ostatnim miesiącu: {{ corona.dateStart }}
      </p>
      <button @click="getCoronaCount" v-if="!loadedCorona">Sprawdź</button>
      <button v-if="loadedCorona">{{ corona.numOfTimes }}</button>
    </aside>
    <div class="slide-corona__fill"></div>
    <div class="slide-corona__fill2"></div>
  </section>
</template>

<script>
import debounce from "lodash/debounce";
import moment from "moment";

export default {
  name: "TheSlide11Corona",
  data() {
    return {
      loadedCorona: false,
      corona: {
        type: Object,
        dateStart: null,
        dateEnd: Date,
        numOfTimes: null,
      },
    };
  },
  methods: {
    getCoronaCount() {
      this.loadedCorona = true;
      this.fetchCorona();
    },
    fetchCorona: debounce(async function() {
      const API = "https://api.nasa.gov/DONKI/CME";
      const KEY = "tQOlgZlTyisnCMawuh75wzIraZpWHsrE7mGDtDuZ";

      const timeNow = moment().format("YYYY-MM");
      const timeBefore = moment()
        .subtract(1, "month")
        .format("YYYY-MM");

      this.corona.dateStart = timeBefore;
      this.corona.dateEnd = timeNow;

      let response = await fetch(
        `${API}?startDate=${timeBefore}-01&endDate=${timeNow}-01&api_key=${KEY}`
      );

      let responseJSON = await response.json();

      this.corona.numOfTimes = responseJSON.length;
    }, 500),
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide-corona {
  @extend %slide-settings;
  grid-template-rows: repeat(9, 16.6666vw);
  grid-template-areas:
    "text text text text text fill"
    "text text text text text fill"
    "text text text text text fill"
    "text text text text text    .   "
    "text text text text text    .   "
    "fil2 . asid    asid asid asid"
    ".    .    asid    asid asid asid"
    ".    .    asid    asid asid asid"
    ".    .    .    .    .   .    ";

  @media screen and (min-width: 700px) {
    grid-template-rows: repeat(4, 6.5vw);
    grid-template-areas:
      "asid asid asid asid text text  text  text  text   text "
      "asid asid asid asid text text  text  text  text   text "
      "asid asid asid asid text text  text  text  text   text "
      ".    .    .    .    .    .     .     .     .      .    ";
  }

  &__text {
    grid-area: text;
    @extend %tile-gray-text;

    p {
      i {
        font-style: italic;
      }
    }
  }

  &__aside {
    grid-area: asid;
    @extend %tile-text-interaction;
    flex-direction: column;
    text-align: center;

    padding: 5%;

    p {
      margin: 0;
    }

    button {
      @extend %button;
      width: 70%;
      height: 35%;
      margin-top: 12%;

      @media screen and (min-width: 700px) {
        width: 75%;
      }
    }
  }

  &__fill {
    grid-area: fill;
    @extend %tile-purple;
  }

  &__fill2 {
    grid-area: fil2;
    @extend %tile-purple;
  }
}
</style>
