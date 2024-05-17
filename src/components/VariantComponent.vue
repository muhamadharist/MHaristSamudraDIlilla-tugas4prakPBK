<template>
  <div class="variant">
    <h3>Komponen Varian</h3>
    <slot></slot>
    <div>
      <button @click="kirimVarian('Ukuran L')">Pilih Ukuran L</button>
      <button @click="kirimVarian('Ukuran M')">Pilih Ukuran M</button>
      <button @click="kirimVarian('Ukuran XL')">Pilih Ukuran XL</button>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    kirimVarian(varian) {
      this.$emit('variant-data', varian);
    },
  },
};
</script>

<style scoped>
.variant {
  padding: 10px;
  border: 1px solid #666;
  border-radius: 6px;
  background-color: #d3d3d3;
}
.variant h3 {
  color: #8e44ad;
}
.variant button {
  padding: 10px;
  border: none;
  border-radius: 5px;
  background-color: #3498db;
  color: white;
  cursor: pointer;
  margin: 5px;
}
.variant button:hover {
  background-color: #2980b9;
}
</style>
