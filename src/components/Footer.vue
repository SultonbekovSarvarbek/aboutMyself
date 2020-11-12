<template>
  <div>
    <footer class="footer">
      <div class="footer__content container">
        <div class="footer__wrapper">
          <div class="footer__contacts">
            <span class="footer__contacts--phone">+998 97 007 7073</span>
            <a
              class="footer__contacts--link"
              target="_blank"
              href="https://t.me/sultonbekovs"
            >
              <div class="footer__contacts--img">
                <img :src="imgSvgTg" />
              </div>
              <p>@sultonbekovs</p>
            </a>
          </div>
          <div class="footer__date">
            <p>{{ currDate }}</p>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import imgSvgTg from "../assets/telegram.svg";
export default {
  data() {
    return {
      imgSvgTg,
      currDate: "",
    };
  },
  created() {
    var currentDate = new Date();
    var currentDateWithFormat = new Date()
      .toJSON()
      .slice(0, 10)
      .replace(/-/g, "/");
    this.currDate = currentDateWithFormat;
  },
};
</script>

<style lang="scss">

.footer {
  &__content {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
}
  position: fixed;
  bottom: 0;
  width: 100%;
  z-index: -1;
  color: $footer-text-color;
  height: 250px;
  &__date {
    margin-left: auto;
  }
  background-image: -webkit-gradient(
    linear,
    left bottom,
    left top,
    color-stop(0, $footer-yellow),
    color-stop(1, $white)
  );
  &__wrapper {
    font-size: 2rem;
    display: flex;

    align-items: center;
    padding: 3rem 0;
  }
  &__contacts {
    text-align: right;
    &--link {
      display: flex;
      align-items: center;
    }
    &--phone {
      font-size: 1rem;
    }
    &--img {
      margin-right: 0.5rem;
      img {
        width: 3rem;
        height: auto;
      }
    }
  }
}
</style>