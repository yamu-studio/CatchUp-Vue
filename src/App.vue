<template>
  <h1>Hello!</h1>
  <!-- データを表示 -->
  <p>{{ onamae }}</p>

  <!-- v-on -->
  <button v-on:click="buttonClick">button</button>
  <!-- 省略系 -->
  <button @click="buttonClick">button</button>
  <p>{{ count }}回押した</p>

  <!-- コンポーネント -->
  <HelloWorld :msg="inputName"></HelloWorld>

  <!-- propsとemitを使う場合
  <AddButton :count="count" @clicked="buttonClick"></AddButton> -->
  <!-- v-modelでやる場合 -->
  <AddButton v-model:count="count"></AddButton>

  <!-- v-bind ⇒単方向バインド -->
  <img v-bind:src="imgSrc" alt="" />
  <img :src="imgSrc" alt="" />
  <p v-bind:class="{ 'font-red': flag }">あいうえお</p>

  <!-- v-model ⇒双方向バインド -->
  <input v-model="inputName" type="text" name="" id="" />
  <!-- ※v-bindはダメ... -->
  <!-- <input v-bind:value="inputName" type="text" name="" id="" /> -->

  <!-- v-if ⇒falseで要素が消える -->
  <p v-if="flag">trueの時(v-if)</p>
  <!-- v-show ⇒falseで要素が見えなくなる -->
  <p v-show="flag">trueの時(v-show)</p>

  <!-- v-for -->
  <p v-for="n in count">{{ n }}</p>
  <p v-for="name in nameList">{{ name }}さん</p>

  <!-- v-forとv-ifの組み合わせ例 -->
  <div v-for="n in nameList">
    <p v-if="n == '鈴木次郎'">{{ n }} さんだよ！</p>
    <p v-else-if="n == '田中太郎'">{{ n }}じゃん！</p>
    <p v-else>その他</p>
  </div>

  <!-- v-html -->
  <div v-html="htmlContent"></div>
</template>

<script setup>
import { ref } from "vue";
import HelloWorld from "./components/HelloWorld.vue";
import AddButton from "./components/AddButton.vue";

// 普通の変数・定数
let onamae = "田中";
console.log(onamae);

const nameList = ["田中太郎", "鈴木次郎", "山田三郎"];
const htmlContent = "<p>HTMLコンテンツだよ！</p>";
const imgSrc = "画像のURL";

// 入力されたデータを入れる
const inputName = ref("yamada");

const flag = ref(false);
const count = ref(0);
// ボタン押したら
// ・countを+1
// ・true⇔false変わる
function buttonClick() {
  count.value++;
  flag.value = !flag.value;
  alert(`${count.value}回押したよう`);
}
</script>

<style scoped>
h1 {
  color: red;
}
.font-red {
  color: red;
}
</style>
