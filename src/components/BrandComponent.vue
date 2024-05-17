<template>
  <div class="brand">
    <h1>Merek Baju</h1>
    <p>Merek Terpilih: {{ merekTerpilih }}</p>
    <p>Ukuran Terpilih: {{ varianTerpilih }}</p>
    <select v-model="merekTerpilih">
      <option disabled value="">Pilih sebuah merek</option>
      <option v-for="merek in merek" :key="merek" :value="merek">{{ merek }}</option>
    </select>
    <model-component v-if="merekTerpilih" @model-data="perbaruiVarian">
      <template v-slot:header>
        <h2>Header: Model Tersedia</h2>
      </template>
      <template v-slot:default>
        <p>Konten dari Merek ke Model</p>
      </template>
      <template v-slot:footer>
        <h2>Footer: Detail Model</h2>
      </template>
    </model-component>
  </div>
</template>

<script>
import ModelComponent from './ModelComponent.vue';

export default {
  components: {
    ModelComponent,
  },
  data() {
    return {
      merek: ['Erigo', 'Blythe', 'Giordano'],
      merekTerpilih: '',
      varianTerpilih: '',
    };
  },
  methods: {
    perbaruiVarian(varian) {
      this.varianTerpilih = varian;
    },
  },
};
</script>

<style scoped>
.brand {
  padding: 20px;
  border: 2px solid #333;
  border-radius: 10px;
  background-color: #f4f4f4;
}
.brand h1 {
  color: #2c3e50;
}
.brand p {
  color: #34495e;
}
.brand select {
  padding: 10px;
  margin: 10px 0;
  border-radius: 5px;
  border: 1px solid #ccc;
}
</style>
