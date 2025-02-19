<template>
  <div v-for="n in nameList">
    <p v-if="n == '鈴木次郎'">{{ n }} さんだよ！</p>
    <p v-else-if="n == '田中太郎'">{{ n }}じゃん！</p>
    <p v-else>その他</p>
  </div>
</template>

<script setup>
defineProps({
  nameList: {
    type: Object,
    required: true,
  },
});
</script>
