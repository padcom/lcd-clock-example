<template>
  <SevenSegmentDisplay :a="a" :b="b" :c="c" :d="d" :e="e" :f="f" :g="g" />
</template>

<script lang="ts" setup>
import { computed } from 'vue'

import SevenSegmentDisplay from './SevenSegmentDisplay.vue'

const props = defineProps({
  digit: { type: String, default: ' ', validator: (value: string) => value.length === 1 },
})

const LOGIC: Record<string, string> = {
  '0': 'abcdef',
  '1': 'bc',
  '2': 'abged',
  '3': 'abcdg',
  '4': 'fgbc',
  '5': 'afgcd',
  '6': 'afedcg',
  '7': 'abc',
  '8': 'abcdefg',
  '9': 'abcdfg',
}

const a = computed(() => (LOGIC[props.digit] || '').includes('a'))
const b = computed(() => (LOGIC[props.digit] || '').includes('b'))
const c = computed(() => (LOGIC[props.digit] || '').includes('c'))
const d = computed(() => (LOGIC[props.digit] || '').includes('d'))
const e = computed(() => (LOGIC[props.digit] || '').includes('e'))
const f = computed(() => (LOGIC[props.digit] || '').includes('f'))
const g = computed(() => (LOGIC[props.digit] || '').includes('g'))
</script>
