<template>
  <div>
    <div class="icon-content">
      <div class="logo-wrap">
        <!-- Generator: Adobe Illustrator 19.0.0, SVG Export Plug-In . SVG Version: 6.00 Build 0)  -->

        <svg
          version="1.1"
          id="vueicon"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          x="0px"
          y="0px"
          viewBox="0 0 122.88 106.42"
          style="enable-background: new 0 0 122.88 106.42"
          xml:space="preserve"
        >
          <g>
            <polygon
              data-llp-duration="4000"
              data-llp-ease="easeLinear"
              class="a"
              points="75.63,0 61.44,24.58 47.25,0 0,0 61.44,106.42 122.88,0 75.63,0"
            />
            <polygon
              data-llp-duration="3000"
              data-llp-ease="easeLinear"
              class="a"
              points="75.63,0 61.44,24.58 47.25,0 24.58,0 61.44,63.85 98.3,0 75.63,0"
            />
          </g>
        </svg>

        <div class="icon">
          <p class="icon__name">VUEJS</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    let el = document.querySelector("#vueicon");
    let myAnimation = new LazyLinePainter(el, {
      strokeColor: "#333",
      strokeWidth: 1,
      delay: 1500,
      ease: "easeInOutExpo",
    });

    function paint() {
      myAnimation.paint();
    }

    paint();
  },
};
</script>
<style lang="scss" scoped>
.icon {
  margin-top: 4rem;
  &__name {
    font-size: 2rem;
    font-weight: 800;
    color: #4dba87;
  }
}
</style>
<style scoped>
#vueicon {
  position: relative;
  display: block;
  width: 100%;
  height: auto;
}
#vueicon {
  fill: none;
  background-color: #4dba871c;
  border-radius: 5px;
  padding: 2rem;
}
</style>