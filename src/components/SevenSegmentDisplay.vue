<template>
  <svg class="seven-segment-display" viewBox="0 0 120 200" width="100" height="200" xmlns="http://www.w3.org/2000/svg">
    <polygon points="12,10 22,20 78,20 88,10 78,0 22,0 12,10" :fill="getFillColor('a')" />
    <polygon points="12,100 22,110 78,110 88,100 78,90 22,90 12,100" :fill="getFillColor('g')" />
    <polygon points="12,190 22,200 78,200 88,190 78,180 22,180 12,190" :fill="getFillColor('d')" />
    <polygon points="10,12 20,22 20,88 10,98 0,88 0,22 10,12" :fill="getFillColor('f')" />
    <polygon points="90,12 100,22 100,88 90,98 80,88 80,22 90,12" :fill="getFillColor('b')" />
    <polygon points="10,102 20,112 20,178 10,188 0,178 0,112 10,102" :fill="getFillColor('e')" />
    <polygon points="90,102 100,112 100,178 90,188 80,178 80,112 90,102" :fill="getFillColor('c')" />
    <circle cx="110" cy="190" r="10" :fill="getFillColor('dp')" />
  </svg>
</template>

<script lang="ts" setup>
const props = defineProps({
  a: { type: Boolean, default: null },
  b: { type: Boolean, default: null },
  c: { type: Boolean, default: null },
  d: { type: Boolean, default: null },
  e: { type: Boolean, default: null },
  f: { type: Boolean, default: null },
  g: { type: Boolean, default: null },
  dp: { type: Boolean, default: null },
})

type Segment = 'a' | 'b' | 'c' | 'd' | 'e' | 'f' | 'g' | 'dp'

function getFillColor(segment: Segment): string {
  return props[segment] ? 'red' : '#181818'
}
</script>

<style lang="postcss" scoped>
.seven-segment-display {
  float: left;
  @apply m-0 p-0;

  & + & {
    @apply ml-4;
  }
}
</style>
