<template>
  <div>
    <div ref="content" class="container">
      <h1>Контакты</h1>
      <div class="contacts__map">
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d23968.706241512326!2d69.20165444369505!3d41.32869366672538!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x38ae8b8bfc9db3ff%3A0x41d08ec9b93150eb!2sGuncha!5e0!3m2!1sen!2s!4v1604998819820!5m2!1sen!2s"
          width="100%"
          height="500"
          frameborder="0"
          style="border: 0"
          allowfullscreen=""
          aria-hidden="false"
          tabindex="0"
        ></iframe>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
.contacts {
  &__map {
    margin-top: 2rem;
  }
}
</style>