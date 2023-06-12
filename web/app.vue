<script setup>
import { VueFlow, MarkerType } from '@vue-flow/core'
import { Background, MiniMap, Controls } from '@vue-flow/additional-components'
import '@vue-flow/core/dist/style.css'
/* import the default theme (optional) */
import '@vue-flow/core/dist/theme-default.css'

const elements = ref([
  { id: '1', type: 'input', label: 'Node 1', position: { x: 250, y: 0 }, class: 'light' },
  { id: '2', type: 'output', label: 'Node 2', position: { x: 100, y: 100 }, class: 'light' },
  { id: '3', label: 'Node 3', position: { x: 400, y: 100 }, class: 'light' },
  { id: '4', label: 'Node 4', position: { x: 150, y: 200 }, class: 'light' },
  { id: '5', type: 'output', label: 'Node 5', position: { x: 300, y: 300 }, class: 'light' },
  { id: 'e1-2', source: '1', target: '2', animated: true },
  { id: 'e1-3', label: 'edge with arrowhead', source: '1', target: '3', markerEnd: MarkerType.ArrowClosed },
  {
    id: 'e4-5',
    type: 'step',
    label: 'step-edge',
    source: '4',
    target: '5',
    style: { stroke: 'orange' },
    labelBgStyle: { fill: 'orange' },
  },
  { id: 'e3-4', type: 'smoothstep', label: 'smoothstep-edge', source: '3', target: '4' },
])
</script>

<template>
  <div>
    <UCard>
      <VueFlow fit-view-on-init v-model="elements">
        <Background />
        <MiniMap />
        <Controls />
      </VueFlow>
    </UCard>
    <!-- <NuxtPage /> -->
  </div>
</template>

<style scoped>
</style>
