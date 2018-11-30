<template>
  <footer class="bottom-footer">
    <div class="util__container">
    <v-footer
      :fixed="fixed"
      app
    >
      <span>&copy; 2017</span>
    </v-footer>
    </div>
  </footer>
</template>

<style lang="scss">
.bottom-footer {
  background: #e3f2ed;
  padding: 40px 0 120px 0;
  text-align: center;
}

.bottom-footer__link {
  color: #8ba19a;
  text-decoration: none;
}
</style>