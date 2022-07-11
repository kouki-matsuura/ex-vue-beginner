<template>
  <div class="left">
    <p>名前：{{ name }}</p>
    <p>年齢：{{ age }}歳</p>
    <p>10年後の年齢:{{ add10 }}歳</p>
    <p>
      趣味：
      <span v-for="hobby of hobbies" :key="hobby">{{ hobby }} </span>
    </p>
    <br />
    <a v-bind:href="rakus">株式会社ラクス</a>
    <br />
    <img v-bind:src="image" alt="" />
    <br />
    <button @click="addElement()" :disabled="canNotClick">ボタン</button>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class Ex02Component extends Vue {
  private name = "";
  private age = 0;
  private add10 = 0;
  private hobbies: string[] = new Array<string>();
  private rakus = "";
  private image = "";
  private canNotClick = false;

  addElement() {
    this.name = "山田太郎";
    this.age = 31;
    this.add10 = this.age + 10;
    this.hobbies = ["スイム", "バイク", "ラン"];
    this.rakus = "https://www.rakus.co.jp/";
    this.image =
      "https://3.bp.blogspot.com/-6PbsTK7_BRM/VmFkA9OHslI/AAAAAAAA1bw/d9wvGFac3pg/s800/stand1_front05_man.png";
    this.canNotClick = true;
  }
}
</script>

<style scoped>
.left {
  text-align: left;
}
</style>
