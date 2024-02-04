<template>
  <div class="ui grid">
    <div class="three wide column" style="background-color: #343a3f">
      <Menu></Menu>
    </div>
    <div class="thirteen wide column" style="background-color: #f3f6f9">
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
