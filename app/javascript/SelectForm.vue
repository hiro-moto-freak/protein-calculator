<template>
  <v-row align="center">
    <v-col cols="3">
      <v-select
        @click="setSubcategories"
        v-model="categories"
        placeholder="食材の種類を選択"
        :items="categoryList"
        item-text="name"
        return-object
      ></v-select>
    </v-col>
    <v-col cols="3">
      <v-select
        @change="setProteinContent"
        v-model="subcategories"
        placeholder="食材を選択"
        :items="categories.children"
        item-text="name"
        item-value="proteinContent"
      ></v-select>
    </v-col>
    <v-col cols="2">{{ proteinContent }}g </v-col>
    <v-col cols="2">
      <input
        class="text-right"
        @click="pmSubmit"
        type="number"
        step="10"
        min="0"
        v-model.number="foodMass"
        placeholder="食材の量を入力"
      />
      g
    </v-col>
    <v-col cols="2">{{ proteinMass.toFixed(1) }}g </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      categories: "",
      subcategories: "",
      proteinContent: 0,
      foodMass: "",
      categoryList: [
        {
          name: "卵・乳製品",
          children: [
            { name: "全卵(一個50g)", proteinContent: 12.5 },
            { name: "卵白(一個当たり33g)", proteinContent: 16.5 },
            { name: "卵黄(一個当たり17g)", proteinContent: 10.5 },
            { name: "牛乳(1g/1ml換算)", proteinContent: 3.4 },
            { name: "無脂肪乳(1g/1ml換算)", proteinContent: 3.9 },
            { name: "低脂肪乳(1g/1ml換算)", proteinContent: 3.9 },
            { name: "ヨーグルト", proteinContent: 3.6 },
            { name: "プロセスチーズ", proteinContent: 22.7 },
          ],
        },
        {
          name: "肉類",
          children: [
            { name: "鶏むね肉(皮なし)", proteinContent: 23.3 },
            { name: "鶏もも肉(皮なし)", proteinContent: 19.0 },
            { name: "鶏むね肉(皮付き)", proteinContent: 21.3 },
            { name: "鶏もも肉(皮付き)", proteinContent: 16.6 },
            { name: "ささみ", proteinContent: 19.0 },
            { name: "豚肉(赤身)", proteinContent: 21.8 },
            { name: "豚肉(脂身付き)", proteinContent: 19.1 },
            { name: "牛肉(赤身)", proteinContent: 20.2 },
            { name: "牛肉(脂身付き)", proteinContent: 18.5 },
            { name: "ソーセージ(1本20g)", proteinContent: 13.2 },
            { name: "ハム(1枚20g)", proteinContent: 16.5 },
            { name: "ベーコン(1枚20g)", proteinContent: 12.9 },
          ],
        },
        {
          name: "魚介類",
          children: [
            { name: "マグロ(赤身)", proteinContent: 26.4 },
            { name: "さけ", proteinContent: 22.3 },
            { name: "たら", proteinContent: 17.6 },
            { name: "さば", proteinContent: 20.6 },
            { name: "アジ", proteinContent: 19.7 },
            { name: "しらす干し", proteinContent: 40.5 },
            { name: "アサリ", proteinContent: 6.0 },
            { name: "イカ", proteinContent: 17.9 },
            { name: "えび", proteinContent: 18.4 },
            { name: "タコ", proteinContent: 16.4 },
            { name: "ツナ缶(1缶70g)", proteinContent: 17.0 },
            { name: "魚肉ソーセージ(1本75g)", proteinContent: 11.5 },
            { name: "ちくわ(1本35g)", proteinContent: 12.2 },
          ],
        },
        {
          name: "大豆製品",
          children: [
            { name: "木綿豆腐", proteinContent: 6.6 },
            { name: "絹ごし豆腐", proteinContent: 4.9 },
            { name: "納豆(1パック30g)", proteinContent: 16.5 },
            { name: "豆乳(1g/1ml換算)", proteinContent: 3.6 },
            { name: "油揚げ(1枚20g)", proteinContent: 18 },
          ],
        },
        {
          name: "主食",
          children: [
            { name: "白米", proteinContent: 2.5 },
            { name: "玄米", proteinContent: 2.8 },
            { name: "食パン", proteinContent: 9.0 },
            { name: "パスタ(乾麺)", proteinContent: 13.0 },
            { name: "うどん(乾麺)", proteinContent: 8.5 },
            { name: "そば(乾麺)", proteinContent: 14.0 },
            { name: "オートミール", proteinContent: 13.7 },
          ],
        },
        {
          name: "プロテインパウダー",
          children: [
            { name: "ホエイプロテイン", proteinContent: 82.0 },
            { name: "ホエイプロテイン(WPI)", proteinContent: 90.0 },
          ],
        },
      ],
    };
  },

  methods: {
    setSubcategories() {
      this.subcategories = "";
    },
    setProteinContent() {
      this.proteinContent = this.subcategories;
    },
    pmSubmit() {
      this.$emit("pm", this.proteinMass);
    },
  },

  computed: {
    proteinMass: function () {
      return (this.foodMass * this.subcategories) / 100;
    },
  },
};
</script>

<style scoped>
p {
  font-size: 2em;
  text-align: center;
}
</style>
