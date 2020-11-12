<template>
  <div>
    <div class="mainbg">
      <div class="mainbg__content">
        <div class="mainbg__wrapper container">
          <div class="mainbg__title">
            <VScrollin :speed="20"> Привет </VScrollin>
          </div>

          <VScrollin class="mainbg__info" :speed="35">
            Меня зовут Сарвар
          </VScrollin>
          <span class="mainbg__subinfo">Фронтенд разработчик</span>

          <a @click="goDown('content')" class="arrow">
            <span></span>
            <span></span>
            <span></span>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VScrollin from "vue-scrollin";

export default {
  components: {
    VScrollin,
  },
  methods: {
    goDown(val) {
      const el = document.getElementById(val);
      console.log(el.offsetTop);
      var top = el.offsetTop;

      window.scrollTo(0, top - 70);
    },
  },
};
</script>


<style lang="scss">
.mainbg {
  width: 100%;
  height: 100vh;
  background-position: center center;
  background-size: cover;
  background-repeat: no-repeat;
  background-image: url("../assets/mainbg2.jpeg");
  &__wrapper {
    font-weight: bold;
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100%;
    justify-content: center;
  }
  &__title {
    font-size: 3rem;
  }

  &__info {
    font-size: 6rem;
  }
  &__subinfo {
    font-size: 2rem;
    color: $base-yellow;
  }
  &__content {
    color: $white;

    background: linear-gradient(rgba(64, 60, 133, 0.653), rgba(1, 1, 1, 0.235));
    height: 100%;
    width: 100%;
  }
}

.arrow {
  display: block;
  position: absolute;
  bottom: 10%;
  left: 50%;
  cursor: pointer;
  transform: translateX(-50%, -10%);
}
.arrow span {
  display: block;
  width: 30px;
  height: 30px;
  border-bottom: 5px solid $base-yellow;
  border-right: 5px solid $base-yellow;
  transform: rotate(45deg);
  margin: -10px;
  animation: animate 2s infinite;
}
.arrow span:nth-child(2) {
  animation-delay: -0.2s;
}
.arrow span:nth-child(3) {
  animation-delay: -0.4s;
}
@keyframes animate {
  0% {
    opacity: 0;
    transform: rotate(45deg) translate(-20px, -20px);
  }
  50% {
    opacity: 1;
  }
  100% {
    opacity: 0;
    transform: rotate(45deg) translate(20px, 20px);
  }
}
</style>
