<template>
  <div class="q-pa-xs example-col-gutter-horizontal">
    <div class="row q-col-gutter-x-md">
      <div class="col">
        <q-input outlined v-model="lecturaAnterior" label="Lectura anterior" />
      </div>
      <div class="col">
        <q-input outlined v-model="lecturaActual" label="Lectura Actual" />
      </div>
    </div>
    <div class="col items-center">
      <q-btn
        color="primary"
        label="Calcular"
        class="q-mt-md"
        @click="calcularDiferencia(lecturaAnterior, lecturaActual)"
      >
      </q-btn>
      <q-input
        outlined
        v-model="importe"
        label="Resultado"
        :value="importe"
        readonly
      />
      <q-input outlined v-model="kilo" label="Consumo" readonly />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
const lecturaAnterior = ref<number>();
const lecturaActual = ref<number>();
const consumo = ref<number | null>(null);
const diferencia = ref<number | null>(null);
const kilo = ref<number | null>(null);
const importe = ref<number | null>(null);
const calcularDiferencia = (
  lecturaAnterior: number | undefined,
  lecturaActual: number | undefined
) => {
  if (lecturaAnterior !== undefined && lecturaActual !== undefined) {
    consumo.value = lecturaActual - lecturaAnterior;
    kilo.value = consumo.value;
  }
  if (consumo.value <= 100) {
    importe.value = consumo.value * 0.33;
  }
  if (consumo.value > 100 && consumo.value <= 150) {
    importe.value = 100 * 0.33;
    consumo.value = consumo.value - 100;
    importe.value += consumo.value * 1.07;
  }
  if (consumo.value > 150 && consumo.value <= 200) {
    importe.value = 100 * 0.33;
    importe.value += 50 * 1.07;
    consumo.value = consumo.value - 150;
    importe.value += consumo.value * 1.43;
  }
  if (consumo.value > 200 && consumo.value <= 250) {
    importe.value = 100 * 0.33;
    importe.value += 50 * 1.07;
    importe.value += 50 * 1.43;
    consumo.value = consumo.value - 200;
    importe.value += consumo.value * 2.46;
  }
  if (consumo.value > 250 && consumo.value <= 300) {
    importe.value = 100 * 0.33;
    importe.value += 50 * 1.07;
    importe.value += 50 * 1.43;
    importe.value += 50 * 2.46;
    consumo.value = consumo.value - 250;
    importe.value += consumo.value * 3.0;
  }
  if (consumo.value > 300 && consumo.value <= 350) {
    importe.value = 100 * 0.33;
    importe.value += 50 * 1.07;
    importe.value += 50 * 1.43;
    importe.value += 50 * 2.46;
    importe.value += 50 * 3.0;
    consumo.value = consumo.value - 300;
    importe.value += consumo.value * 4.0;
  }
  if (consumo.value > 350 && consumo.value <= 400) {
    importe.value = 100 * 0.33;
    importe.value += 50 * 1.07;
    importe.value += 50 * 1.43;
    importe.value += 50 * 2.46;
    importe.value += 50 * 3.0;
    importe.value += 50 * 4.0;
    consumo.value = consumo.value - 350;
    importe.value += consumo.value * 5.0;
  }
  if (consumo.value > 400 && consumo.value <= 450) {
    importe.value = 100 * 0.33;
    importe.value += 50 * 1.07;
    importe.value += 50 * 1.43;
    importe.value += 50 * 2.46;
    importe.value += 50 * 3.0;
    importe.value += 50 * 4.0;
    importe.value += 50 * 5.0;
    consumo.value = consumo.value - 400;
    importe.value += consumo.value * 6.0;
  }
  if (consumo.value > 450 && consumo.value <= 500) {
    importe.value = 100 * 0.33;
    importe.value += 50 * 1.07;
    importe.value += 50 * 1.43;
    importe.value += 50 * 2.46;
    importe.value += 50 * 3.0;
    importe.value += 50 * 4.0;
    importe.value += 50 * 5.0;
    importe.value += 50 * 6.0;
    consumo.value = consumo.value - 450;
    importe.value += consumo.value * 7.0;
  }
  if (consumo.value > 500 && consumo.value <= 600) {
    importe.value = 100 * 0.33;
    importe.value += 50 * 1.07;
    importe.value += 50 * 1.43;
    importe.value += 50 * 2.46;
    importe.value += 50 * 3.0;
    importe.value += 50 * 4.0;
    importe.value += 50 * 5.0;
    importe.value += 50 * 6.0;
    importe.value += 50 * 7.0;
    consumo.value = consumo.value - 500;
    importe.value += consumo.value * 11.05;
  }
  if (consumo.value > 600 && consumo.value <= 700) {
    importe.value = 100 * 0.33;
    importe.value += 50 * 1.07;
    importe.value += 50 * 1.43;
    importe.value += 50 * 2.46;
    importe.value += 50 * 3.0;
    importe.value += 50 * 4.0;
    importe.value += 50 * 5.0;
    importe.value += 50 * 6.0;
    importe.value += 50 * 7.0;
    importe.value += 50 * 11.05;
    consumo.value = consumo.value - 600;
    importe.value += consumo.value * 11.81;
  }
  if (consumo.value > 700 && consumo.value <= 1000) {
    importe.value = 100 * 0.33;
    importe.value += 50 * 1.07;
    importe.value += 50 * 1.43;
    importe.value += 50 * 2.46;
    importe.value += 50 * 3.0;
    importe.value += 50 * 4.0;
    importe.value += 50 * 5.0;
    importe.value += 50 * 6.0;
    importe.value += 50 * 7.0;
    importe.value += 50 * 11.05;
    importe.value += 50 * 11.81;
    consumo.value = consumo.value - 700;
    importe.value += consumo.value * 12.31;
  }

  if (consumo.value > 1000 && consumo.value <= 1800) {
    importe.value = 100 * 0.33;
    importe.value += 50 * 1.07;
    importe.value += 50 * 1.43;
    importe.value += 50 * 2.46;
    importe.value += 50 * 3.0;
    importe.value += 50 * 4.0;
    importe.value += 50 * 5.0;
    importe.value += 50 * 6.0;
    importe.value += 50 * 7.0;
    importe.value += 50 * 11.05;
    importe.value += 50 * 11.81;
    importe.value += 50 * 12.31;
    consumo.value = consumo.value - 1000;
    importe.value += consumo.value * 13.5;
  }
  if (consumo.value > 1800 && consumo.value <= 2600) {
    importe.value = 100 * 0.33;
    importe.value += 50 * 1.07;
    importe.value += 50 * 1.43;
    importe.value += 50 * 2.46;
    importe.value += 50 * 3.0;
    importe.value += 50 * 4.0;
    importe.value += 50 * 5.0;
    importe.value += 50 * 6.0;
    importe.value += 50 * 7.0;
    importe.value += 50 * 11.05;
    importe.value += 50 * 11.81;
    importe.value += 50 * 12.31;
    importe.value += 50 * 13.5;
    consumo.value = consumo.value - 1800;
    importe.value += consumo.value * 14.75;
  }
  if (consumo.value > 2600 && consumo.value <= 3400) {
    importe.value = 100 * 0.33;
    importe.value += 50 * 1.07;
    importe.value += 50 * 1.43;
    importe.value += 50 * 2.46;
    importe.value += 50 * 3.0;
    importe.value += 50 * 4.0;
    importe.value += 50 * 5.0;
    importe.value += 50 * 6.0;
    importe.value += 50 * 7.0;
    importe.value += 50 * 11.05;
    importe.value += 50 * 11.81;
    importe.value += 50 * 12.31;
    importe.value += 50 * 13.5;
    importe.value += 50 * 14.75;
    consumo.value = consumo.value - 2600;
    importe.value += consumo.value * 16.13;
  }
  if (consumo.value > 3400 && consumo.value <= 4200) {
    importe.value = 100 * 0.33;
    importe.value += 50 * 1.07;
    importe.value += 50 * 1.43;
    importe.value += 50 * 2.46;
    importe.value += 50 * 3.0;
    importe.value += 50 * 4.0;
    importe.value += 50 * 5.0;
    importe.value += 50 * 6.0;
    importe.value += 50 * 7.0;
    importe.value += 50 * 11.05;
    importe.value += 50 * 11.81;
    importe.value += 50 * 12.31;
    importe.value += 50 * 13.5;
    importe.value += 50 * 14.75;
    importe.value += 50 * 16.13;
    consumo.value = consumo.value - 3400;
    importe.value += consumo.value * 17.44;
  }
  if (consumo.value > 4200 && consumo.value <= 5000) {
    importe.value = 100 * 0.33;
    importe.value += 50 * 1.07;
    importe.value += 50 * 1.43;
    importe.value += 50 * 2.46;
    importe.value += 50 * 3.0;
    importe.value += 50 * 4.0;
    importe.value += 50 * 5.0;
    importe.value += 50 * 6.0;
    importe.value += 50 * 7.0;
    importe.value += 50 * 11.05;
    importe.value += 50 * 11.81;
    importe.value += 50 * 12.31;
    importe.value += 50 * 13.5;
    importe.value += 50 * 14.75;
    importe.value += 50 * 16.13;
    importe.value += 50 * 17.44;
    consumo.value = consumo.value - 4200;
    importe.value += consumo.value * 18.75;
  }
  if (consumo.value > 5000) {
    importe.value = 100 * 0.33;
    importe.value += 50 * 1.07;
    importe.value += 50 * 1.43;
    importe.value += 50 * 2.46;
    importe.value += 50 * 3.0;
    importe.value += 50 * 4.0;
    importe.value += 50 * 5.0;
    importe.value += 50 * 6.0;
    importe.value += 50 * 7.0;
    importe.value += 50 * 11.05;
    importe.value += 50 * 11.81;
    importe.value += 50 * 12.31;
    importe.value += 50 * 13.5;
    importe.value += 50 * 14.75;
    importe.value += 50 * 16.13;
    importe.value += 50 * 17.44;
    importe.value += 50 * 18.75;
    consumo.value = consumo.value - 5000;
    importe.value += consumo.value * 25.0;
  }
};
</script>
<style lang="sass">
.example-col-gutter-horizontal
  .my-content
    padding: 10px 15px
    background: rgba(#999,.15)
    border: 1px solid rgba(#999,.2)
</style>
