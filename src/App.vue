<template>
  <div class="ui grid">
    <div class="three wide column" style="background-color: #343a3f">
      <Menu></Menu>
    </div>

    <div class="thirteen wide column" style="background-color: #f3f6f9">
      <hr />
      <h1>Tablo Komponent</h1>
      <dkom></dkom>
      <hr />
      <hr />
      <h1>Istatıstık Komponent</h1>
      <div class="ui statistics">
        <div class="statistic veri">
          <div
            class="value"
            style="margin-top: 30px; color: white; font-weight: 700"
          >
            31,200
          </div>
          <div class="label">Views</div>
        </div>
      </div>
      <hr />
      <hr />
      <h1>bildirim Komponent</h1>
      <bildirim></bildirim>
      <hr />
      <hr />
      <h1>sayac Komponent</h1>
      <sayac></sayac>
      <hr />
      <hr />
      <h1>info Komponent</h1>
      <info></info>
      <hr />
    </div>
  </div>
</template>
<style>
.veri {
  width: 280px;
  height: 140px;

  background-color: #14a2b8;
}
</style>
<script>
import Dkom from "./components/Dkom.vue";
import Bildirim from "./components/Bildirim.vue";
import Sayac from "./components/Sayac.vue";
import Menu from "./components/Menu.vue";
import Info from "./components/Info.vue";

export default {
  name: "App",
  components: {
    Dkom,
    Bildirim,
    Sayac,
    Menu,
    Info,
  },
};
</script>
