<template>
  <svg class="sd" viewBox="0 0 30 200" width="30" height="200" xmlns="http://www.w3.org/2000/svg">
    <circle cx="15" cy="60" r="15" :fill="getFillColor()" />
    <circle cx="15" cy="140" r="15" :fill="getFillColor()" />
  </svg>
</template>

<script lang="ts" setup>
const props = defineProps({
  on: { type: Boolean, default: null },
})

function getFillColor(): string {
  return props.on ? 'red' : '#181818'
}
</script>

<style lang="postcss" scoped>
.sd {
  float: left;
  @apply mx-4;
}
</style>
