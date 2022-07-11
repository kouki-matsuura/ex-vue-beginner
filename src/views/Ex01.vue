<template>
  <div class="left">
    <p>名前：{{ name }}</p>
    <p>年齢：{{ age }}</p>
    <p>10年後の年齢:{{ age + 10 }}</p>
    <p>
      趣味：
      <span v-for="hobby of hobbies" :key="hobby">{{ hobby }} </span>
    </p>
    <br />
    <a v-bind:href="rakus">株式会社ラクス</a>
    <br />
    <img v-bind:src="men" alt="" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class Ex01Component extends Vue {
  private name = "山田太郎";
  private age = 31;
  private hobbies = new Array<string>("スイム", "バイク", "ラン");
  private rakus = "https://www.rakus.co.jp/";
  private men =
    "https://3.bp.blogspot.com/-6PbsTK7_BRM/VmFkA9OHslI/AAAAAAAA1bw/d9wvGFac3pg/s800/stand1_front05_man.png";
}
</script>

<style scoped></style>
