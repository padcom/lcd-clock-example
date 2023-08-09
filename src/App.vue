<template>
  <TimeDisplay :time="time" />
</template>

<script lang="ts" setup>
import TimeDisplay from './components/TimeDisplay.vue'
import { useNow } from '@vueuse/core'

const time = useNow()
</script>
