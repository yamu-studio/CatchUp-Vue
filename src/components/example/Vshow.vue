<template>
  <p v-show="flag">trueの時(v-show)</p>
</template>

<script setup>
defineProps({
  flag: {
    type: Boolean,
    required: true,
  },
});
</script>
