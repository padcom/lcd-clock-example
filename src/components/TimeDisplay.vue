<template>
  <DigitDisplay :digit="digits[0]" class="" />
  <DigitDisplay :digit="digits[1]" class="" />
  <SeparatorDisplay :on="decimalSeparatorState" />
  <DigitDisplay :digit="digits[2]" class="" />
  <DigitDisplay :digit="digits[3]" class="" />
</template>

<script lang="ts" setup>
import { computed } from 'vue'
import DigitDisplay from './DigitDisplay.vue'
import SeparatorDisplay from './SeparatorDisplay.vue'

const props = defineProps({
  time: { type: Date, default: () => new Date() },
})

const digits = computed(() => {
  const date = props.time.toISOString()

  return date.substring(11, 13) + date.substring(14, 16)
})

const decimalSeparatorState = computed(() => props.time.getSeconds() % 2 === 0)
</script>
