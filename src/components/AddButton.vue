<template>
  <button @click="buttonClick">button</button>
  <p>{{ count }}回押した</p>
</template>

<script setup>
// props ⇒データを受け取る(変更できない)
// const  = defineProps({
//   count: {
//     type: Number,
//     required: true,
//   },
// });

// emit ⇒イベントを自作できる
// const emit = defineEmits(["clicked"]);

// v-modelならこれでデータを結び付ける
const count = defineModel("count");

function buttonClick() {
  count.value++;
  alert(`${count.value}回押したよう`);
  // emit("clicked");
}
</script>
