<template>
  {{ state }}
</template>

<script lang="ts" setup>
import { onUpdated, ref } from 'vue'

const props = defineProps({
  d0: { type: Boolean, default: null },
  d1: { type: Boolean, default: null },
  d2: { type: Boolean, default: null },
  d3: { type: Boolean, default: null },
  d4: { type: Boolean, default: null },
  d5: { type: Boolean, default: null },
  d6: { type: Boolean, default: null },
  d7: { type: Boolean, default: null },
  en: { type: Boolean, default: null },
  cs: { type: Boolean, default: null },
  rw: { type: Boolean, default: null },
})

const BITS = ['d0', 'd1', 'd2', 'd3', 'd4', 'd5', 'd6', 'd7'] as const

const state = ref(0)

onUpdated(() => {
  if (props.rw && props.en && props.cs) {
    state.value = BITS.reduce((acc, line, index) => acc + (props[line] ? 1 << index : 0), 0)
  }
})
</script>
