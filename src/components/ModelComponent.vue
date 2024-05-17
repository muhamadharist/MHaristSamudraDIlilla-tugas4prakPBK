<template>
  <div class="model">
    <slot name="header"></slot>
    <h2>Komponen Model</h2>
    <slot></slot>
    <variant-component @variant-data="teruskanData">
      <template v-slot:default>
        <p>Konten dari Model ke Ukuran</p>
      </template>
    </variant-component>
    <slot name="footer"></slot>
  </div>
</template>

<script>
import VariantComponent from './VariantComponent.vue';

export default {
  components: {
    VariantComponent,
  },
  methods: {
    teruskanData(varian) {
      this.$emit('model-data', varian);
    },
  },
};
</script>

<style scoped>
.model {
  padding: 15px;
  border: 1px solid #999;
  border-radius: 8px;
  background-color: #e0e0e0;
  margin: 10px 0;
}
.model h2 {
  color: #2980b9;
}
</style>
