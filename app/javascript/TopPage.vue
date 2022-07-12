<template>
  <v-app>
    <v-container fluid>
      <v-card width="600" height="300" class="mx-auto mb-8">
        {{ totalProteinMass.toFixed(1) }}
      </v-card>
      <v-card dark color="teal" width="1200" class="mx-auto px-5 mb-2">
        <v-row>
          <v-col cols="3" color="red">食材の種類</v-col>
          <v-col cols="3">食材</v-col>
          <v-col cols="2" class="text-center">100g当たり</v-col>
          <v-col cols="2" class="text-center">食材の量</v-col>
          <v-col cols="2" class="text-center">タンパク質量</v-col>
        </v-row>
      </v-card>
      <v-card tile width="1200" class="mx-auto px-5">
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
import SelectForm from "./SelectForm.vue";

export default {
  components: {
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

<style scoped>
</style>
