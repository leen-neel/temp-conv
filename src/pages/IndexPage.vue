<template>
  <q-page class="flex flex-center">
    <div class="row q-gutter-lg">
      <q-card class="bg-primary card">
        <q-card-section>
          <div class="text-h2 text-center text-weight-bolder">C</div>
        </q-card-section>

        <q-card-section class="text-h4 text-weight-bold text-center">
          15 <sup>o</sup>
        </q-card-section>
      </q-card>

      <q-card class="bg-primary card">
        <q-card-section>
          <div class="text-h2 text-center text-weight-bolder">F</div>
        </q-card-section>

        <q-card-section class="text-h4 text-weight-bold text-center">
          15 <sup>o</sup>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "IndexPage",
});
</script>

<style lang="scss" scoped>
.card {
  width: 20vw;
  // height: 50vh;
}
</style>
