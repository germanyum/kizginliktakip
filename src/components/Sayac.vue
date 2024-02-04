<template>
  <div class="row">
    <div
      class="ui equal width center aligned padded grid"
      style="border: 3px solid red"
    >
      <div class="row">
        <div class="column" v-for="x in 10" key="x">
          <div class="ui red inverted statistic">
            <div class="value">{{ x }}</div>
            <div class="label">inek sayısı</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Sayac",
};
</script>
