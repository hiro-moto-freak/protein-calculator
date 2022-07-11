<template>
  <v-app>
    <v-container fluid>
      {{ totalProteinMass.toFixed(1) }}
      <SelectForm @pm="setProteinMass1" />
      <SelectForm @pm="setProteinMass2" />
      <SelectForm @pm="setProteinMass3" />
      <SelectForm @pm="setProteinMass4" />
      <SelectForm @pm="setProteinMass5" />
      <SelectForm @pm="setProteinMass6" />
      <SelectForm @pm="setProteinMass7" />
      <SelectForm @pm="setProteinMass8" />
      <SelectForm @pm="setProteinMass9" />
      <SelectForm @pm="setProteinMass10" />
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
      proteinMass1: 0,
      proteinMass2: 0,
      proteinMass3: 0,
      proteinMass4: 0,
      proteinMass5: 0,
      proteinMass6: 0,
      proteinMass7: 0,
      proteinMass8: 0,
      proteinMass9: 0,
      proteinMass10: 0,
    };
  },
  methods: {
    setProteinMass1(pm) {
      this.proteinMass1 = pm;
    },
    setProteinMass2(pm) {
      this.proteinMass2 = pm;
    },
    setProteinMass3(pm) {
      this.proteinMass3 = pm;
    },
    setProteinMass4(pm) {
      this.proteinMass4 = pm;
    },
    setProteinMass5(pm) {
      this.proteinMass5 = pm;
    },
    setProteinMass6(pm) {
      this.proteinMass6 = pm;
    },
    setProteinMass7(pm) {
      this.proteinMass7 = pm;
    },
    setProteinMass8(pm) {
      this.proteinMass8 = pm;
    },
    setProteinMass9(pm) {
      this.proteinMass9 = pm;
    },
    setProteinMass10(pm) {
      this.proteinMass10 = pm;
    },
  },
  computed: {
    totalProteinMass: function () {
      return (
        this.proteinMass1 +
        this.proteinMass2 +
        this.proteinMass3 +
        this.proteinMass4 +
        this.proteinMass5 +
        this.proteinMass6 +
        this.proteinMass7 +
        this.proteinMass8 +
        this.proteinMass9 +
        this.proteinMass10
      );
    },
  },
};
</script>

<style scoped>
</style>
