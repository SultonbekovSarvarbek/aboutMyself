<template>
  <div>
    <header class="header">
      <div class="container">
        <div class="header__wrapper">
          <nav class="nav">
            <ul class="nav__links">
              <li class="nav__link">
                <a target="_blank" href="https://const.tech/">
                  <span class="nav__comlink"> Сonst.Tech </span></a
                >
              </li>

              <li v-for="link in links" :key="link.id" class="nav__link">
                <router-link :to="link.path"> {{ link.link }} </router-link>
              </li>
            </ul>
          </nav>
          <div>
            <ul class="nav__icons">
              <li class="nav__icon">
                <a target="_blank" href="https://t.me/sultonbekovs">
                  <img :src="imgSvgTg"
                /></a>
              </li>
              <li class="nav__icon">
                <a
                  target="_blank"
                  href="https://www.facebook.com/profile.php?id=100008357823829"
                >
                  <img :src="imgSvgFb"
                /></a>
              </li>
            </ul>
          </div>
          <div class="nav__mobile">
            <svg
              @click="activeMobNav"
              class="ham hamRotate ham1"
              viewBox="0 0 100 100"
              width="80"
              :class="{ active: showNav }"
            >
              <path
                class="line top"
                d="m 30,33 h 40 c 0,0 9.044436,-0.654587 9.044436,-8.508902 0,-7.854315 -8.024349,-11.958003 -14.89975,-10.85914 -6.875401,1.098863 -13.637059,4.171617 -13.637059,16.368042 v 40"
              />
              <path class="line middle" d="m 30,50 h 40" />
              <path
                class="line bottom"
                d="m 30,67 h 40 c 12.796276,0 15.357889,-11.717785 15.357889,-26.851538 0,-15.133752 -4.786586,-27.274118 -16.667516,-27.274118 -11.88093,0 -18.499247,6.994427 -18.435284,17.125656 l 0.252538,40"
              />
            </svg>
          </div>
        </div>
      </div>
    </header>
    <mobileNav @click="onClickMobNav" :class="{ mobileActive: showNav }" />
  </div>
</template>

<script>
// telegram Icon
import imgSvgTg from "../assets/telegram.svg";
// Facebook Icon
import imgSvgFb from "../assets/facebook.svg";
import mobileNav from "../components/MobileNav";

export default {
  components: {
    mobileNav,
  },
  data() {
    return {
      showNav: false,
      links: [
        {
          link: "Обо мне",
          path: "/",
        },
        {
          link: "Контакты",
          path: "/contacts",
        },
      ],
      imgSvgTg,
      imgSvgFb,
    };
  },

  methods: {
    activeMobNav() {
      this.showNav = !this.showNav;
    },
    onClickMobNav(value) {
      this.showNav = value;
    },
  },
};
</script>
<style lang="scss">
.mobileActive {
  transform: translateX(0);
  transition: all 0.4s;
}
.ham {
  cursor: pointer;
  -webkit-tap-highlight-color: transparent;
  transition: transform 400ms;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.hamRotate.active {
  transform: rotate(45deg);
}
.hamRotate180.active {
  transform: rotate(180deg);
}
.line {
  fill: none;
  transition: stroke-dasharray 400ms, stroke-dashoffset 400ms;
  stroke: $white;
  stroke-width: 5.5;
  stroke-linecap: round;
}
.ham1 .top {
  stroke-dasharray: 40 139;
}
.ham1 .bottom {
  stroke-dasharray: 40 180;
}
.ham1.active .top {
  stroke-dashoffset: -98px;
}
.ham1.active .bottom {
  stroke-dashoffset: -138px;
}
.header {
  background-color: $header-bg;
  position: fixed;
  top: 0;
  z-index: 19;
  width: 100%;
  &__wrapper {
    color: $white;
    font-weight: bold;
    font-size: 1.5rem;
    padding: 1.5rem 0.8rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
}

.nav {
  &__mobile {
    display: none;
  }
  &__icon:not(:first-child) {
    margin-left: 1rem;
  }

  &__links,
  &__icons {
    img {
      width: 2.5rem;
      height: auto;
    }
    display: flex;
  }

  &__link {
    position: relative;
    &:not(:last-child) {
      margin-right: 2rem;
    }
    &:hover {
      color: $base-yellow;
      transition: all 0.2s;
    }
    a {
      &.router-link-exact-active {
        position: relative;
        &:after {
          display: block;
          visibility: visible;
          opacity: 1;
          bottom: 0;
        }
        color: $base-yellow;
      }
      &:after {
        position: absolute;
        bottom: 15px;
        content: "";
        width: 100%;
        height: 3px;
        background-color: $white;
        display: block;
        opacity: 0;
        visibility: hidden;
        transition: all 0.4s;
      }
      &:hover {
        &:after {
          bottom: 0;
          visibility: visible;
          opacity: 1;
        }
      }
    }
  }
  &__comlink {
    color: $base-yellow;
  }
}
</style>
