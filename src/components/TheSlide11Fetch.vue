<template>
  <div>
    <section class="slide-fetch">
      <div class="slide-fetch__caption">
        <h2>{{ title }}</h2>
      </div>
      <div class="slide-fetch__image">
        <img :src="photo" alt="Betelgeza" />
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "TheSlide11Fetch",
  data() {
    return {
      photo: this.item.links[0].href,
      title: this.item.data[0].title,
    };
  },
  props: {
    item: {
      type: Object,
      required: true,
    },
    index: {
      type: Number,
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.slide-fetch {
  @extend %slide-settings;
  width: 100vw;
  grid-template-rows: repeat(6, 16.6666vw);
  grid-template-areas:
    "cap  cap  cap  .    .    .     "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    "img  img  img  img  img  img   "
    ".    .    .    .    .    .     ";

  &__caption {
    grid-area: cap;
    font-size: 4.5vw;
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
}
</style>
