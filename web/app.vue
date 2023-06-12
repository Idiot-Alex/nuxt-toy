<script setup>
import { VueFlow } from '@vue-flow/core'
import { Background } from '@vue-flow/background'
import { MiniMap } from '@vue-flow/minimap'
import { Controls } from '@vue-flow/controls'

const elements = ref([
  // Nodes
  // An input node, specified by using `type: 'input'`
  { id: '1', type: 'input', label: 'Node 1', position: { x: 250, y: 5 } },

  // Default nodes, you can omit `type: 'default'`
  { id: '2', label: 'Node 2', position: { x: 100, y: 100 }, },
  { id: '3', label: 'Node 3', position: { x: 400, y: 100 } },

  // An output node, specified by using `type: 'output'`
  { id: '4', type: 'output', label: 'Node 4', position: { x: 400, y: 200 } },

  // Edges
  // Most basic edge, only consists of an id, source-id and target-id
  { id: 'e1-3', source: '1', target: '3' },

  // An animated edge
  { id: 'e1-2', source: '1', target: '2', animated: true },
])
</script>

<template>
  <div>
    <UCard zoom-1>
      <VueFlow fit-view-on-init v-model="elements" :default-viewport="{ zoom: 1.5 }" :min-zoom="0.2" :max-zoom="4">
        <Background />
        <MiniMap pannable zoomable />
        <Controls showZoom showFitView />
      </VueFlow>
    </UCard>
    <!-- <NuxtPage /> -->
  </div>
</template>

<style scoped>
/* import the required styles */
@import "@vue-flow/core/dist/style.css";
/* import the default theme (optional) */
@import "@vue-flow/core/dist/theme-default.css";
/* import default minimap styles */
@import "@vue-flow/minimap/dist/style.css";
/* import default controls styles */
@import "@vue-flow/controls/dist/style.css";
</style>
