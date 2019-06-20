<template>
  <div id="app" class="container">
    <div class="grid">
      <Vheader></Vheader>
      <search></search>
      <main>
        <h1>No te debes perder 1</h1>
        <div class="row-section">
          <vcard></vcard>
          <vcard></vcard>
          <vcard></vcard>
        </div>
        <h1>No te debes perder 2</h1>
        <div class="row-section">
          <vcard></vcard>
          <vcard></vcard>
          <vcard></vcard>
        </div>
        <h1>No te debes perder 3</h1>
        <div class="row-section">
          <vcard></vcard>
          <vcard></vcard>
          <vcard></vcard>
        </div>
      </main>
    </div>
  </div>
</template>

<script>
import Vheader from "./components/header/Vheader.vue";
import search from "./components/search/search.vue";
import Vcard from "./components/card/Vcard.vue";
export default {
  name: "app",
  data() {
    return {
      msg: "Hola Vue.js App"
    };
  },
  components: {
    Vheader,
    search,
    Vcard
  }
};
</script>

<style lang="scss">
@import "./scss/style.scss";
</style>
