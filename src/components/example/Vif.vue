<template>
  <p v-if="flag">trueの時(v-if)</p>
</template>

<script setup>
defineProps({
  flag: {
    type: Boolean,
    required: true,
  },
});
</script>
