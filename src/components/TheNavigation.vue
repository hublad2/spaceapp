<template>
  <nav v-if="scrolledPastSlide1" class="nav-wrapper">
    <ul>
      <li
        v-if="scrolledToTop == false"
        @click="moveToSlide(navigationList[currentPosition - 1].id)"
      >
        <div class="button-background">
          <i class="fas fa-arrow-up"></i>
        </div>
      </li>
      <li v-for="navPoint in navigationList" :key="navPoint.id">
        <button
          :class="{ whitefont: navPoint.isReached }"
          @click="moveToSlide(navPoint.id)"
        >
          {{ navPoint.text }}
        </button>
      </li>
      <li v-if="scrolledToBottom == false">
        <div
          class="button-background"
          @click="moveToSlide(navigationList[currentPosition + 1].id)"
        >
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
      navigationList: [
        {
          id: "#slide1",
          text: "Początki",
          isReached: false,
        },
        {
          id: "#star-evolution",
          text: "Ewolucja gwiazd",
          isReached: false,
        },
        {
          id: "#solar-system",
          text: "Układ Słoneczny",
          isReached: false,
        },
        {
          id: "#beyond-neptune",
          text: "Za Neptunem",
          isReached: false,
        },
        {
          id: "#galaxy",
          text: "Galaktyka",
          isReached: false,
        },
        {
          id: "#hubble",
          text: "Prawo Hubble'a",
          isReached: false,
        },
      ],
      scrolledToTop: false,
      scrolledToBottom: false,
      scrolledPastSlide1: false,
      checkpoints: [],
      currentPosition: null,
    };
  },
  created() {
    window.addEventListener("scroll", this.isUserOnTop);
    window.addEventListener("scroll", this.isUserOnBottom);
    window.addEventListener("scroll", this.isUserPastHero);
    window.addEventListener("scroll", this.updateNavList);
  },
  mounted() {
    this.findAllCheckpoints();
  },
  methods: {
    moveToSlide(navPoint) {
      /* document.querySelector(navPoint).scrollIntoView({
        behavior: "smooth",
      }); */

      let elementToScrollTo = document.querySelector(navPoint);
      let y =
        elementToScrollTo.getBoundingClientRect().top + window.pageYOffset;
      console.log(y);
      window.scrollTo({ top: y, behavior: "smooth" });
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

      if (window.scrollY >= slide1Element.offsetTop) {
        this.scrolledPastSlide1 = true;
      } else {
        this.scrolledPastSlide1 = false;
      }
    },
    findAllCheckpoints() {
      // eslint-disable-next-line
      this.navigationList.forEach((navPoint) => {
        this.checkpoints.push(document.querySelector(navPoint.id));
      });
    },
    updateNavList() {
      // When at the end of checkpoint list
      for (let i = 0; i < this.checkpoints.length; i++) {
        if (i == this.checkpoints.length - 1) {
          if (window.scrollY >= this.checkpoints[i].offsetTop) {
            for (let j = 0; j < this.navigationList.length; j++) {
              if (j == i) {
                this.navigationList[j].isReached = true;
                this.currentPosition = j;
              } else {
                this.navigationList[j].isReached = false;
              }
            }
          }
          return;
        }

        if (
          window.scrollY >= this.checkpoints[i].offsetTop &&
          window.scrollY < this.checkpoints[i + 1].offsetTop
        ) {
          for (let j = 0; j < this.navigationList.length; j++) {
            if (j == i) {
              this.navigationList[j].isReached = true;
              this.currentPosition = j;
            } else {
              this.navigationList[j].isReached = false;
            }
          }
        }
      }
    },
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
      margin: 0.9vw 0;
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
        font-size: 1vw;
        width: 9vw;
        max-width: 200px;
        height: 4vw;
        max-height: 70px;
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

  .whitefont {
    color: $colorFont1;
  }
}
</style>
