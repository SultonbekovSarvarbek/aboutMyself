<template>
  <div class="mobilenav">
    <nav>
      <ul>
        <li
          class="mobilenav__link"
          @click="onClickLink"
          v-for="link in links"
          :key="link.id"
        >
          <router-link :to="link.path"> {{ link.name }} </router-link>
        </li>
      </ul>
    </nav>
    <div></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          name: "Обо мне",
          path: "/",
        },
        {
          name: "Контакты",
          path: "/contacts",
        },
      ],
    };
  },
  methods: {
    onClickLink(event) {
      this.$emit("click", false);
    },
  },
};
</script>

<style lang="scss">
.mobilenav {
  &__link {
    &:not(:last-child) {
      margin-bottom: 1.5rem;
    }
    font-size: 1.7rem;
    font-weight: bold;
  }
  padding: 2rem;
  position: fixed;
  top: 84px;
  height: 100%;
  z-index: 29;
  right: 0;
  width: 320px;
  transform: translateX(320px);
  background-color: #333;
  color: $white;
  transition: all 0.4s;
}
</style>