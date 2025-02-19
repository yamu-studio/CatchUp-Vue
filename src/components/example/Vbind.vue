<template>
  <p v-bind:class="{ 'font-red': flag }">あいうえお</p>
</template>

<script setup>
defineProps({
  flag: {
    type: Boolean,
    required: true,
  },
});
</script>
