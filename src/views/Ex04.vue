<template>
  <div>
    <input type="text" v-model.number="num1" /><br />
    <input type="text" v-model.number="num2" /><br />
    <input type="text" v-model.number="num3" /><br />
    税抜き価格:{{ price.toLocaleString() }}円
    <br />
    税込価格：{{ priceWithTax.toLocaleString() }}円
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class Ex04Component extends Vue {
  private num1 = 0;
  private num2 = 0;
  private num3 = 0;

  get price(): number {
    return this.num1 + this.num2 + this.num3;
  }

  get priceWithTax(): number {
    return Math.floor(this.price * 1.1);
  }
}
</script>

<style scoped></style>
