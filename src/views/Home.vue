<template>
  <div>
    <div class="about">
      <div class="container">
        <div class="about__wrapper">
          <h1>Обо мне</h1>
          <div class="about__item">
            <div class="about__img">
              <img src="../assets/sarvar_img.jpg" alt="" />
            </div>
            <div class="about__info">
              <h1>Султонбеков Сарварбек</h1>
              <div class="about__info--pos">
                <p>Фронтенд разработчик</p>
                <p>21 года</p>
                <p>Проживаю в городе Ташкент</p>
              </div>
              <div class="about__cv">
                <a
                  target="_blank"
                  href="https://drive.google.com/file/d/1quI-lZ8uQf4kjpLAm9Y0JGYAkogztZpG/view"
                  class="btn cvbtn"
                >
                  Резюме
                </a>
              </div>
            </div>
          </div>
          <div class="about__skillswrapper">
            <h1>Навыки</h1>
            <div class="about__skills">
              <htmlicon />
              <cssicon />
              <jsicon />
              <vueicon />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import LazyLinePainter from "lazy-line-painter";
import htmlicon from "../assets/html";
import jsicon from "../assets/icons/jsicon";
import cssicon from "../assets/icons/cssicon";
import vueicon from "../assets/icons/vueicon";
export default {
  components: {
    htmlicon,
    jsicon,
    cssicon,
    vueicon,
  },
};
</script>

<style lang="scss">
.about {
  &__cv {
    margin-top: 5rem;
    .cvbtn {
      display: inline-block;
      background: $btn-color;
      padding: 1rem;
      text-align: center;
      border-radius: 5px;
      color: $black;
      font-size: 1.4rem;
      font-weight: normal;
    }
  }
  &__skillswrapper {
    margin-top: 5rem;
  }
  &__wrapper {
    text-align: left;
  }
  &__skills {
    margin-top: 5rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  &__item {
    display: flex;
    align-items: flex-start;
    margin-top: 2rem;
  }
  &__info {
    margin-left: 1.5rem;
    &--pos {
      margin-top: 2rem;
      font-size: 1.3rem;
      p {
        margin-bottom: 1rem;
      }
    }
  }
  &__wrapper {
    padding: 5rem 0;
    position: relative;
    z-index: 1;
    &:after {
      right: 0;
      position: absolute;
      top: 10%;
      z-index: -1;
      content: "";
      width: 304px;

      height: 264px;
      background: url("../assets/dots.png") right top;
    }
  }
  &__img {
    width: 300px;
    height: auto;

    img {
      border-radius: 7px;
      display: block;
      width: 100%;
      height: auto;
    }
  }
}
</style>