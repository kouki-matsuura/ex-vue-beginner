<template>
  <div>
    <input type="text" v-model.number="num1" />
    +
    <input type="text" v-model.number="num2" />
    =
    {{ answer }}
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class Ex03Component extends Vue {
  private num1 = 0;
  private num2 = 0;

  get answer(): number {
    return this.num1 + this.num2;
  }
}
</script>

<style scoped></style>
