<template>
  <div class="row">
    <div
      class="ui equal width center aligned padded grid"
      style="border: 3px solid red"
    >
      <div class="row">
        <div class="column ten wide">
          <table class="ui celled striped table">
            <thead>
              <tr>
                <th colspan="2">Bildirimler</th>
                <th>Onay</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="x in inek" key="x.id">
                <td class="collapsing"><i class="circle icon"></i> TR112222</td>
                <td>
                  <a class="ui teal tag label">Kızgılık</a
                  ><a v-if="x.kiz" class="ui olive tag label">Tohumlama</a>
                  <a v-if="x.gebe" class="ui red tag label">Doğum</a>
                </td>
                <td class="right aligned collapsing">
                  <button class="circular ui icon button">
                    <i class="icon thumbs up"></i>
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
  name: "Bildirim",
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
