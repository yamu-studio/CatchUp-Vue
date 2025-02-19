<template>
  <p v-for="n in count">{{ n }}</p>
</template>

<script setup>
defineProps({
  count: {
    type: Number,
    required: true,
  },
});
</script>
