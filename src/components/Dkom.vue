<template>
  <table class="ui celled striped table">
    <thead>
      <tr>
        <th>küpe</th>
        <th>kızgın</th>
        <th>gebe</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td v-for="x in arama" :key="x.id">
          <div class="ui search">
            <div class="ui icon input">
              <input
                v-model="x.deger"
                :kutu-no="x"
                class="prompt"
                type="text"
                placeholder="Common passwords..."
              />
              <i class="search icon"></i>
            </div>
            <div class="results"></div>
          </div>
        </td>
      </tr>
      <tr v-for="x in sayfa" :key="x.id">
        <td class="collapsing"><i class="folder icon"></i> {{ x.kupe }}</td>
        <td>{{ x.kizgin }}</td>
        <td class="right aligned collapsing">{{ x.gebe }}</td>
      </tr>
    </tbody>
    <tfoot>
      <tr>
        <th colspan="3">
          <div class="ui right floated pagination menu">
            <a class="icon item">
              <i class="left chevron icon"></i>
            </a>
            <a class="item" v-if="sayfano > 1" @click="sgit(sayfano - 1)">{{
              sayfano - 1
            }}</a>
            <a
              class="item"
              style="color: red"
              v-if="sayfa.length <= sayfalamas"
              @click="sgit(sayfano)"
              >{{ sayfano }}</a
            >
            <a
              class="item"
              style="color: green"
              v-if="
                filtre.length / sayfalamas > sayfano &&
                filtre.length > sayfalamas
              "
              @click="sgit(sayfano + 1)"
              >{{ sayfano + 1 }}</a
            >

            <a class="icon item">
              <i class="right chevron icon"></i>
            </a>
          </div>
        </th>
      </tr>
    </tfoot>
  </table>
</template>
<script>
export default {
  name: "Dkom",
  data() {
    return {
      arama: [{}, {}],

      items: [
        {
          id: 1,
          kupe: "4041371028390191aa",
          gebe: true,
          kizgin: true,
        },
        {
          id: 2,
          kupe: "4488130906715aa",
          gebe: true,
          kizgin: true,
        },
        {
          id: 3,
          kupe: "4017956248314aa",
          gebe: true,
          kizgin: false,
        },
        {
          id: 4,
          kupe: "4439206995795651aa",
          gebe: true,
          kizgin: true,
        },
        {
          id: 5,
          kupe: "4017952508075aa",
          gebe: true,
          kizgin: false,
        },
        {
          id: 6,
          kupe: "4017955529813",
          gebe: true,
          kizgin: false,
        },
        {
          id: 7,
          kupe: "4041593704034",
          gebe: false,
          kizgin: false,
        },
        {
          id: 8,
          kupe: "4017952146228494",
          gebe: true,
          kizgin: true,
        },
        {
          id: 9,
          kupe: "4041598453815355",
          gebe: false,
          kizgin: true,
        },
        {
          id: 10,
          kupe: "4017957028244196",
          gebe: true,
          kizgin: false,
        },
        {
          id: 11,
          kupe: "4041595721076588",
          gebe: false,
          kizgin: true,
        },
        {
          id: 12,
          kupe: "4711142810884",
          gebe: true,
          kizgin: true,
        },
        {
          id: 13,
          kupe: "4041376256095",
          gebe: false,
          kizgin: false,
        },
        {
          id: 14,
          kupe: "4017953086723429",
          gebe: false,
          kizgin: false,
        },
        {
          id: 15,
          kupe: "4151366020172551",
          gebe: true,
          kizgin: true,
        },
        {
          id: 16,
          kupe: "4017955141966703",
          gebe: true,
          kizgin: false,
        },
        {
          id: 17,
          kupe: "4017950614158755",
          gebe: false,
          kizgin: false,
        },
        {
          id: 18,
          kupe: "4041592956586381",
          gebe: true,
          kizgin: true,
        },
        {
          id: 19,
          kupe: "4041378198931",
          gebe: true,
          kizgin: true,
        },
        {
          id: 20,
          kupe: "4041378055495",
          gebe: true,
          kizgin: true,
        },
        {
          id: 21,
          kupe: "4671943206762859",
          gebe: true,
          kizgin: false,
        },
        {
          id: 22,
          kupe: "4017950708279459",
          gebe: true,
          kizgin: false,
        },
        {
          id: 23,
          kupe: "4041594395584",
          gebe: false,
          kizgin: false,
        },
        {
          id: 24,
          kupe: "4017956187694",
          gebe: true,
          kizgin: false,
        },
        {
          id: 25,
          kupe: "4570832926394329",
          gebe: true,
          kizgin: false,
        },
        {
          id: 26,
          kupe: "4041377483453820",
          gebe: false,
          kizgin: false,
        },
        {
          id: 27,
          kupe: "4041372340062369",
          gebe: true,
          kizgin: false,
        },
        {
          id: 28,
          kupe: "4041370319878948",
          gebe: false,
          kizgin: false,
        },
        {
          id: 29,
          kupe: "4041376531759311",
          gebe: false,
          kizgin: false,
        },
        {
          id: 30,
          kupe: "4017958917455430",
          gebe: false,
          kizgin: false,
        },
        {
          id: 31,
          kupe: "4041595331740045",
          gebe: false,
          kizgin: true,
        },
        {
          id: 32,
          kupe: "4193571900447",
          gebe: true,
          kizgin: false,
        },
        {
          id: 33,
          kupe: "4017952647543",
          gebe: true,
          kizgin: true,
        },
        {
          id: 34,
          kupe: "4334089395106711",
          gebe: true,
          kizgin: false,
        },
        {
          id: 35,
          kupe: "4041374018208",
          gebe: true,
          kizgin: false,
        },
        {
          id: 36,
          kupe: "4017958438292676",
          gebe: true,
          kizgin: true,
        },
        {
          id: 37,
          kupe: "4017952121804",
          gebe: false,
          kizgin: false,
        },
        {
          id: 38,
          kupe: "4017955000724",
          gebe: false,
          kizgin: true,
        },
        {
          id: 39,
          kupe: "4978390165850640",
          gebe: false,
          kizgin: true,
        },
        {
          id: 40,
          kupe: "4367223232392933",
          gebe: true,
          kizgin: false,
        },
        {
          id: 41,
          kupe: "4041374082841240",
          gebe: true,
          kizgin: true,
        },
        {
          id: 42,
          kupe: "4622314135980055",
          gebe: false,
          kizgin: false,
        },
        {
          id: 43,
          kupe: "4041593425903",
          gebe: false,
          kizgin: true,
        },
        {
          id: 44,
          kupe: "4041597637579507",
          gebe: true,
          kizgin: true,
        },
        {
          id: 45,
          kupe: "4740885492802641",
          gebe: false,
          kizgin: true,
        },
        {
          id: 46,
          kupe: "4041599179918",
          gebe: true,
          kizgin: true,
        },
        {
          id: 47,
          kupe: "4017953771524",
          gebe: true,
          kizgin: false,
        },
        {
          id: 48,
          kupe: "4041596502025075",
          gebe: false,
          kizgin: false,
        },
        {
          id: 49,
          kupe: "4017956065209831",
          gebe: false,
          kizgin: true,
        },
        {
          id: 50,
          kupe: "4041593819276558",
          gebe: false,
          kizgin: false,
        },
        {
          id: 51,
          kupe: "4017957776711420",
          gebe: false,
          kizgin: false,
        },
        {
          id: 52,
          kupe: "4017957272974",
          gebe: false,
          kizgin: false,
        },
        {
          id: 53,
          kupe: "4041594252753558",
          gebe: false,
          kizgin: false,
        },
        {
          id: 54,
          kupe: "4017952101426",
          gebe: false,
          kizgin: true,
        },
        {
          id: 55,
          kupe: "4041595188517",
          gebe: false,
          kizgin: true,
        },
        {
          id: 56,
          kupe: "4041594896540",
          gebe: true,
          kizgin: false,
        },
        {
          id: 57,
          kupe: "4017951350459449",
          gebe: true,
          kizgin: true,
        },
        {
          id: 58,
          kupe: "4041371690147960",
          gebe: false,
          kizgin: false,
        },
        {
          id: 59,
          kupe: "4041591065872088",
          gebe: true,
          kizgin: false,
        },
        {
          id: 60,
          kupe: "4041591471776",
          gebe: true,
          kizgin: false,
        },
        {
          id: 61,
          kupe: "4041377684396166",
          gebe: true,
          kizgin: true,
        },
        {
          id: 62,
          kupe: "4966132268239618",
          gebe: false,
          kizgin: false,
        },
        {
          id: 63,
          kupe: "4041592377345",
          gebe: true,
          kizgin: false,
        },
        {
          id: 64,
          kupe: "4017958119463",
          gebe: false,
          kizgin: true,
        },
        {
          id: 65,
          kupe: "4017955138219",
          gebe: false,
          kizgin: false,
        },
        {
          id: 66,
          kupe: "4017954738506",
          gebe: true,
          kizgin: false,
        },
        {
          id: 67,
          kupe: "4041373058635",
          gebe: true,
          kizgin: false,
        },
        {
          id: 68,
          kupe: "4017959078502",
          gebe: false,
          kizgin: true,
        },
        {
          id: 69,
          kupe: "4041591572979",
          gebe: false,
          kizgin: true,
        },
        {
          id: 70,
          kupe: "4017957399728355",
          gebe: true,
          kizgin: true,
        },
        {
          id: 71,
          kupe: "4041371000025856",
          gebe: true,
          kizgin: false,
        },
        {
          id: 72,
          kupe: "4414356138886559",
          gebe: true,
          kizgin: false,
        },
        {
          id: 73,
          kupe: "4017953369580454",
          gebe: true,
          kizgin: true,
        },
        {
          id: 74,
          kupe: "4511418573442",
          gebe: false,
          kizgin: true,
        },
        {
          id: 75,
          kupe: "4017958896698",
          gebe: true,
          kizgin: true,
        },
        {
          id: 76,
          kupe: "4017950415227668",
          gebe: true,
          kizgin: false,
        },
        {
          id: 77,
          kupe: "4041372151142",
          gebe: false,
          kizgin: false,
        },
        {
          id: 78,
          kupe: "4041596797616000",
          gebe: false,
          kizgin: true,
        },
        {
          id: 79,
          kupe: "4041378738207",
          gebe: false,
          kizgin: true,
        },
        {
          id: 80,
          kupe: "4041598915767",
          gebe: false,
          kizgin: true,
        },
        {
          id: 81,
          kupe: "4017953990546",
          gebe: false,
          kizgin: false,
        },
        {
          id: 82,
          kupe: "4041374120492048",
          gebe: true,
          kizgin: true,
        },
        {
          id: 83,
          kupe: "4017959627191",
          gebe: false,
          kizgin: false,
        },
        {
          id: 84,
          kupe: "4041594912291338",
          gebe: false,
          kizgin: true,
        },
        {
          id: 85,
          kupe: "4041379540123",
          gebe: false,
          kizgin: true,
        },
        {
          id: 86,
          kupe: "4041377693106",
          gebe: true,
          kizgin: false,
        },
        {
          id: 87,
          kupe: "4976982590322",
          gebe: true,
          kizgin: false,
        },
        {
          id: 88,
          kupe: "4041375320793",
          gebe: true,
          kizgin: true,
        },
        {
          id: 89,
          kupe: "4041599826146",
          gebe: false,
          kizgin: true,
        },
        {
          id: 90,
          kupe: "4041379796386",
          gebe: false,
          kizgin: false,
        },
        {
          id: 91,
          kupe: "4127425067180504",
          gebe: false,
          kizgin: false,
        },
        {
          id: 92,
          kupe: "4782728105953618",
          gebe: true,
          kizgin: true,
        },
        {
          id: 93,
          kupe: "4041591882642",
          gebe: false,
          kizgin: false,
        },
        {
          id: 94,
          kupe: "4041379700538292",
          gebe: false,
          kizgin: false,
        },
        {
          id: 95,
          kupe: "4041591484751574",
          gebe: false,
          kizgin: false,
        },
        {
          id: 96,
          kupe: "4017957703622",
          gebe: true,
          kizgin: true,
        },
        {
          id: 97,
          kupe: "4041371446766",
          gebe: false,
          kizgin: true,
        },
        {
          id: 98,
          kupe: "4041599473246",
          gebe: true,
          kizgin: true,
        },
        {
          id: 99,
          kupe: "4260972732339335",
          gebe: true,
          kizgin: true,
        },
        {
          id: 100,
          kupe: "4041373601491",
          gebe: true,
          kizgin: true,
        },
      ],
      sayfano: 1,
      sayfalamas: 4,
      sayfa: [],
      filtre: [],
    };
  },
  methods: {
    sgit: function (deger) {
      this.sayfa = this.filtre.slice(
        deger * this.sayfalamas - this.sayfalamas,
        deger * this.sayfalamas
      );
      this.sayfano = deger;
    },
  },

  watch: {
    arama: {
      deep: true,
      handler() {
        //let xs = event.target.getAttribute("kutu-no");
        let kupe = this.arama[0].deger;
        console.log();
        var x = this.items.filter((deger) => deger.kupe.toString().match(kupe));
        this.filtre = x;
        this.sgit(1);
        console.log(this.sayfa);
      },
    },
  },
};
</script>
