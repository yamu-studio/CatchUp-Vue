<template>
  <img :src="imgSrc" alt="" />
</template>

<script setup>
defineProps({
  imgSrc: {
    type: String,
    required: true,
  },
});
</script>
