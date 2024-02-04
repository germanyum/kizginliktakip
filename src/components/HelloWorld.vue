<template>
  <div class="ui equal width center aligned padded grid">
    <div class="row">
      <div class="black three wide column">
        <div class="ui column centered">
          <div class="column">
            <div class="ui vertical menu">
              <a class="item"> Home </a>
              <a class="item"> Messages </a>
              <a class="item"> Friends </a>
            </div>
          </div>
        </div>
      </div>
      <div class="olive column">
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
                      <td class="collapsing">
                        <i class="circle icon"></i> TR112222
                      </td>
                      <td>
                        <a class="ui teal tag label">Kızgılık</a
                        ><a v-if="x.kiz" class="ui olive tag label"
                          >Tohumlama</a
                        >
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
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
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
