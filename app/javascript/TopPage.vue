<template>
  <v-app>
    <Header />
    <v-container fluid mt-5>
      <v-card flat class="mx-auto pa-2 mb-5 text-center">
        <v-card flat>ProCalは簡単タンパク質量計算サイトです。 </v-card>
        <v-card flat>
          食材を選択し、量を入力してください。自動で総タンパク質量を計算します
        </v-card>
      </v-card>
      <v-card tile width="600" class="mx-auto mb-8 pb-5">
        <v-card
          dark
          tile
          width="600"
          color="blue-grey"
          class="of-rem text-center py-1 mb-5"
        >
          計算結果
        </v-card>
        <v-card flat class="d-flex">
          <v-card flat class="ml-auto mr-1 mt-auto mb-1 otf-rem">
            総タンパク質量は
          </v-card>
          <v-card
            outlined
            min-width="230"
            height="110"
            class="pr-3 text-right font-weight-light five-rem"
          >
            {{ totalProteinMass.toFixed(1) }}
          </v-card>
          <v-card flat height="110" class="font-weight-light five-rem">
            g
          </v-card>
          <v-card flat class="mr-auto ml-1 mb-1 mt-auto otf-rem">です</v-card>
        </v-card>
        <v-card></v-card>
      </v-card>
      <v-card
        tile
        dark
        color="blue-grey"
        width="1200"
        class="mx-auto px-5 mb-2"
      >
        <v-row>
          <v-col cols="3" color="red">食材の種類</v-col>
          <v-col cols="3">食材</v-col>
          <v-col cols="2" class="text-center">100g当たり</v-col>
          <v-col cols="2" class="text-center">食材の量</v-col>
          <v-col cols="2" class="text-center">タンパク質量</v-col>
        </v-row>
      </v-card>
      <v-card tile width="1200" class="mx-auto mb-8 px-5">
        <SelectForm @pm="setProteinMass01" />
        <SelectForm @pm="setProteinMass02" />
        <SelectForm @pm="setProteinMass03" />
        <SelectForm @pm="setProteinMass04" />
        <SelectForm @pm="setProteinMass05" />
        <SelectForm @pm="setProteinMass06" />
        <SelectForm @pm="setProteinMass07" />
        <SelectForm @pm="setProteinMass08" />
        <SelectForm @pm="setProteinMass09" />
        <SelectForm @pm="setProteinMass10" />
      </v-card>
    </v-container>
  </v-app>
</template>

<script>
import Header from "./Header.vue";
import SelectForm from "./SelectForm.vue";

export default {
  components: {
    Header,
    SelectForm,
  },
  data() {
    return {
      proteinMass01: 0,
      proteinMass02: 0,
      proteinMass03: 0,
      proteinMass04: 0,
      proteinMass05: 0,
      proteinMass06: 0,
      proteinMass07: 0,
      proteinMass08: 0,
      proteinMass09: 0,
      proteinMass10: 0,
    };
  },
  methods: {
    setProteinMass01(pm) {
      this.proteinMass01 = pm;
    },
    setProteinMass02(pm) {
      this.proteinMass02 = pm;
    },
    setProteinMass03(pm) {
      this.proteinMass03 = pm;
    },
    setProteinMass04(pm) {
      this.proteinMass04 = pm;
    },
    setProteinMass05(pm) {
      this.proteinMass05 = pm;
    },
    setProteinMass06(pm) {
      this.proteinMass06 = pm;
    },
    setProteinMass07(pm) {
      this.proteinMass07 = pm;
    },
    setProteinMass08(pm) {
      this.proteinMass08 = pm;
    },
    setProteinMass09(pm) {
      this.proteinMass09 = pm;
    },
    setProteinMass10(pm) {
      this.proteinMass10 = pm;
    },
  },
  computed: {
    totalProteinMass: function () {
      return (
        this.proteinMass01 +
        this.proteinMass02 +
        this.proteinMass03 +
        this.proteinMass04 +
        this.proteinMass05 +
        this.proteinMass06 +
        this.proteinMass07 +
        this.proteinMass08 +
        this.proteinMass09 +
        this.proteinMass10
      );
    },
  },
};
</script>

<style>
</style>
