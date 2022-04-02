<template>
  <q-page class="flex flex-center">
    <div
      class="q-gutter-lg"
      :class="{ row: !$q.screen.lt.md, column: $q.screen.lt.md }"
    >
      <q-card class="bg-primary card">
        <q-card-section>
          <div class="text-h1 text-center text-weight-bolder">C</div>
        </q-card-section>

        <q-card-section
          v-if="!isEditingCel"
          @click="isEditingCel = true"
          class="text-h3 text-weight-bold text-center cursor-pointer"
        >
          {{ celsius }}°
        </q-card-section>

        <q-card-section>
          <q-input
            color="white"
            v-if="isEditingCel"
            v-model="celsius"
            type="number"
            @blur="toFar"
            @keydown.prevent.enter="toFar"
            filled
          />
        </q-card-section>
      </q-card>

      <q-card class="bg-primary card">
        <q-card-section>
          <div class="text-h1 text-center text-weight-bolder">F</div>
        </q-card-section>

        <q-card-section
          v-if="!isEditingFar"
          @click="isEditingFar = true"
          class="text-h3 text-weight-bold text-center cursor-pointer"
        >
          {{ farenheit }}°
        </q-card-section>

        <q-card-section>
          <q-input
            color="white"
            v-if="isEditingFar"
            v-model="farenheit"
            type="number"
            @blur="toCel"
            @keydown.prevent.enter="toCel"
            filled
          />
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "IndexPage",

  setup() {
    const celsius = ref(0);
    const farenheit = ref(0);

    const isEditingCel = ref(false);
    const isEditingFar = ref(false);

    const toCel = () => {
      celsius.value = Math.round((farenheit.value - 32) * (5 / 9));
      isEditingFar.value = false;
    };

    const toFar = () => {
      farenheit.value = Math.round(celsius.value * (9 / 5) + 32);
      isEditingCel.value = false;
    };

    return {
      celsius,
      farenheit,

      isEditingCel,
      isEditingFar,

      toCel,
      toFar,
    };
  },
});
</script>

<style lang="scss" scoped>
.card {
  width: 200px;
  color: white;
  border-radius: 16px;
  font-family: "Mukta", sans-serif;
}
</style>
