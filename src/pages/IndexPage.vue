<template>
  <q-page class="flex flex-center">
    <div class="row q-gutter-lg">
      <q-card class="bg-primary card">
        <q-card-section>
          <div class="text-h2 text-center text-weight-bolder">C</div>
        </q-card-section>

        <q-card-section class="text-h4 text-weight-bold text-center">
          {{ celsius }} <sup>o</sup>
        </q-card-section>
      </q-card>

      <q-card class="bg-primary card">
        <q-card-section>
          <div class="text-h2 text-center text-weight-bolder">F</div>
        </q-card-section>

        <q-card-section class="text-h4 text-weight-bold text-center">
          {{ farenheit }} <sup>o</sup>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>

<script>
import { defineComponent, ref, watch } from "vue";

export default defineComponent({
  name: "IndexPage",

  setup() {
    const celsius = ref(0);
    const farenheit = ref(55);

    const toCel = () => {
      celsius.value = Math.round((farenheit.value - 32) * (5 / 9));
    };

    return {
      celsius,
      farenheit,
    };
  },
});
</script>

<style lang="scss" scoped>
.card {
  width: 20vw;
  height: 35vh;
}
</style>
