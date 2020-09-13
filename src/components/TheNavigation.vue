<template>
  <nav v-if="scrolledPastSlide1" class="nav-wrapper">
    <ul>
      <li v-if="scrolledToTop == false">
        <div class="button-background">
          <i class="fas fa-arrow-up"></i>
        </div>
      </li>
      <li v-for="navPoint in navigationList" :key="navPoint.id">
        <button @click="moveToSlide(navPoint.id)">{{ navPoint.text }}</button>
      </li>
      <li v-if="scrolledToBottom == false">
        <div class="button-background">
          <i class="fas fa-arrow-down"></i>
        </div>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "TheNavigation",
  data() {
    return {
      navigationList: {
        navPoint1: {
          id: "#slide1",
          text: "Początki",
        },
        navPoint2: {
          id: "#star-evolution",
          text: "Ewolucja gwiazd",
        },
        navPoint3: {
          id: "#now",
          text: "Obecnie",
        },
        navPoint4: {
          id: "#solar-system",
          text: "Układ Słoneczny",
        },
      },
      scrolledToTop: false,
      scrolledToBottom: false,
      scrolledPastSlide1: false,
    };
  },
  created() {
    window.addEventListener("scroll", this.isUserOnTop);
    window.addEventListener("scroll", this.isUserOnBottom);
    window.addEventListener("scroll", this.isUserPastHero);
  },
  methods: {
    moveToSlide(navPoint) {
      document.querySelector(navPoint).scrollIntoView({
        behavior: "smooth",
      });
    },
    isUserOnTop() {
      let slide1Element = document.querySelector("#star-evolution");
      if (window.scrollY < slide1Element.offsetTop) {
        this.scrolledToTop = true;
      } else {
        this.scrolledToTop = false;
      }
    },
    isUserOnBottom() {
      if (window.innerHeight + window.scrollY >= document.body.offsetHeight) {
        this.scrolledToBottom = true;
      } else {
        this.scrolledToBottom = false;
      }
    },
    isUserPastHero() {
      let slide1Element = document.querySelector("#slide1");

      if (window.scrollY > slide1Element.offsetTop) {
        this.scrolledPastSlide1 = true;
      } else {
        this.scrolledPastSlide1 = false;
      }
    },
    updateWhereUserIs() {},
  },
};
</script>

<style scoped lang="scss">
@import "../scss/_variables.scss";
@import "../scss/_extensions.scss";

.nav-wrapper {
  display: none;
  position: fixed;
  right: 4%;
  top: 50%;
  transform: translateY(-50%);

  @media screen and (min-width: 700px) {
    display: block;
  }

  ul {
    display: flex;
    flex-direction: column;

    li {
      margin: 1.1vw 0;
      display: flex;
      justify-content: center;
      border-radius: 50%;

      i {
        font-size: 2.2vw;
        color: white;
        z-index: 1;
      }

      button {
        @extend %tile-purple;
        border: none;
        font-size: 1.2vw;
        width: 9vw;
        height: 4vw;
        cursor: pointer;
      }
    }
  }

  .direction {
    border-radius: 50%;
    width: 4vw;
    height: 4vw;
  }

  .button-background {
    @extend %tile-purple;
    padding: 1.5vw;
    border-radius: 50%;
    z-index: 0;
    cursor: pointer;
  }
}
</style>
