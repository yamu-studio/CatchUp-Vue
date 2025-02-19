<template>
  <h1>Hello!</h1>
  <!-- データを表示 -->
  <p>{{ onamae }}</p>

  <!-- 
  ※あくまでコンポーネント(部品)でまとめて並べれば見やすいよねという例です
  ↓無理やりコンポーネントにしてるのでコンポーネント自体は参考にしないでください 
  -->

  <!-- Helloコンポ -->
  <HelloWorld :msg="inputName"></HelloWorld>

  <!-- AddButtonコンポ -->
  <AddButton v-model:count="count" />

  <!-- 画像コンポ -->
  <Img :img-src="imgSrc" />

  <!-- v-bindコンポ -->
  <Vbind :flag="flag" />

  <!-- v-modelコンポ -->
  <InputForm v-model:inputName="inputName" />

  <!-- v-if -->
  <Vif :flag="flag" />
  <!-- v-show -->
  <Vshow :flag="flag" />

  <!-- 数字のv-forコンポ -->
  <VforCount :count="count" />

  <!-- 名前リストのv-forコンポ -->
  <VforName :name-list="nameList" />

  <!-- v-htmlコンポ -->
  <Show :html-content="htmlContent" />
</template>

<script setup>
import { ref } from "vue";
import HelloWorld from "./components/HelloWorld.vue";
import AddButton from "./components/AddButton.vue";
import Img from "./components/example/Img.vue";
import InputForm from "./components/example/InputForm.vue";
import Vif from "./components/example/Vif.vue";
import Vshow from "./components/example/Vshow.vue";
import VforCount from "./components/example/VforCount.vue";
import VforName from "./components/example/VforName.vue";
import Show from "./components/example/Show.vue";
import Vbind from "./components/example/Vbind.vue";

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
