<template>
  <div v-html="htmlContent"></div>
</template>

<script setup>
defineProps({
  htmlContent: {
    type: String,
    required: true,
  },
});
</script>
