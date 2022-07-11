<template>
  <div>
    <div class="error" v-text="nameError"></div>
    <br />
    名前:<br />
    <input type="text" v-model.trim="name" /><br />
    <div class="error" v-text="ageError"></div>
    <br />
    年齢:<br />
    <input type="text" v-model.number="age" /><br />
    <div class="error" v-text="commentError"></div>
    <br />
    コメント:<br />
    <textarea v-model.trim="comment" /><br />
    <button @click="check()">入力値チェック</button>
    <hr />
    <br />
    <div v-text="complete"></div>
    <br />
    入力値：<br />
    名前：{{ name }}<br />
    年齢：{{ age }}<br />
    コメント：
    <pre>{{ comment }}</pre>
    <br />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class Ex05Component extends Vue {
  private nameError = "";
  private name = "";
  private ageError = "";
  private age = "";
  private commentError = "";
  private comment = "";
  private complete = "";

  check(): void {
    if (this.name === "") {
      this.nameError = "名前が入力されていません";
    } else {
      this.nameError = "";
    }

    if (this.age === "" || !this.numCheck(this.age)) {
      this.ageError = "年齢が入力されていません";
    } else {
      this.ageError = "";
    }

    if (this.comment === "") {
      this.commentError = "コメントが入力されていません";
    } else {
      this.commentError = "";
    }

    if (
      this.nameError === "" &&
      this.ageError === "" &&
      this.commentError === ""
    ) {
      this.complete = "送信が完了しました";
    }
  }

  numCheck(age: string): boolean {
    let reg = new RegExp(/^[0-9]*$/);
    let res = reg.test(age);
    return res;
  }
}
</script>

<style scoped>
.error {
  color: red;
}
</style>
