<template>
  <div class="text-5xl">
    <ComplexPart cs en :rw="rw" :d0="d0" :d1="d1" :d2="d2" :d3="d3" :d4="d4" :d5="d5" :d6="d6" :d7="d7" />
    <br>
    <button class="btn" @click="testme">Testme</button>
  </div>
</template>

<script lang="ts" setup>
import { ref, nextTick } from 'vue'
import ComplexPart from './components/ComplexPart.vue'

const d0 = ref(false)
const d1 = ref(false)
const d2 = ref(false)
const d3 = ref(false)
const d4 = ref(false)
const d5 = ref(false)
const d6 = ref(false)
const d7 = ref(false)
const rw = ref(false)

async function testme() {
  d0.value = Math.random() > 0.5
  d1.value = Math.random() > 0.5
  d2.value = Math.random() > 0.5
  d3.value = Math.random() > 0.5
  d4.value = Math.random() > 0.5
  d5.value = Math.random() > 0.5
  d6.value = Math.random() > 0.5
  d7.value = Math.random() > 0.5

  rw.value = true
  await nextTick()
  rw.value = false
}
</script>
