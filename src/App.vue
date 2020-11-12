<template>
  <div id="app" :class="{ bodyLock: bodyLock }">
    <!-- main header -->
    <Header @click="activeMobNav" />
    <!-- main preview -->
    <Preview />
    <div class="content">
      <div id="content" class="content__mg">
        <transition name="fade" mode="out-in">
          <router-view />
        </transition>
      </div>
    </div>
    <!-- footer -->
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header";
import Preview from "./components/MainPreview";
import Footer from "./components/Footer";
export default {
  components: {
    Header,
    Preview,
    Footer,
  },
  data() {
    return {
      bodyLock: "",
    };
  },
  methods: {
    activeMobNav(value) {
      this.bodyLock = value;
    },
  },
};
</script>
<style lang="scss">
.fade-enter-active,
.fade-leave-active {
  transition-duration: 0.3s;
  transition-property: opacity;
  transition-timing-function: ease;
}
.fade-enter,
.fade-leave-active {
  opacity: 0;
}
.content {
  z-index: 1;
  background-color: $white;
  &__mg {
    padding: 5rem 0;
    margin-bottom: 250px;
  }
}
</style>