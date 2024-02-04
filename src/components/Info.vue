<template>
  <div class="row">
    <div
      class="ui equal width center aligned padded grid"
      style="border: 3px solid red"
    >
      <div class="row">
        <div class="column">
          <table class="ui celled table">
            <thead>
              <tr>
                <th>Küpe No</th>
                <th>Yaşı</th>
                <th>Tohumlamaya kalan Süre</th>
                <th>Tohumlandı</th>
                <th>Gebe</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="x in inek" key="x.id">
                <td data-label="Name">{{ x.id }}</td>
                <td data-label="Age">{{ x.age }}</td>
                <td data-label="Job">{{ x.ovu }}</td>
                <td>
                  <button
                    class="positive ui button"
                    v-bind:class="{ disabled: !x.kiz }"
                  >
                    ok
                  </button>
                </td>
                <td>
                  <button
                    class="positive ui button"
                    v-bind:class="{ disabled: !x.gebe }"
                  >
                    ok
                  </button>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Info",
  data() {
    return {
      inek: [
        {
          id: "TR112233",
          age: "2yıl 3 gün",
          ovu: 34,
          kiz: true,
          gebe: true,
        },
        {
          id: "TR112233",
          age: "2yıl 3 gün",
          ovu: 34,
          kiz: false,
          gebe: true,
        },
        {
          id: "TR112233",
          age: "2yıl 3 gün",
          ovu: 34,
          kiz: true,
          gebe: false,
        },
      ],
    };
  },
};
</script>
