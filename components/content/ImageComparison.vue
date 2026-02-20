<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps<{
  beforeSrc: string
  afterSrc: string
  beforeAlt?: string
  afterAlt?: string
}>()

const sliderPosition = ref(50)
const isDragging = ref(false)

const handleMouseDown = () => {
  isDragging.value = true
}

const handleMouseUp = () => {
  isDragging.value = false
}

const handleMouseMove = (e: MouseEvent) => {
  if (!isDragging.value) return
  
  const rect = (e.currentTarget as HTMLElement).getBoundingClientRect()
  const x = e.clientX - rect.left
  const percentage = (x / rect.width) * 100
  sliderPosition.value = Math.max(0, Math.min(100, percentage))
}

const handleTouchMove = (e: TouchEvent) => {
  const rect = (e.currentTarget as HTMLElement).getBoundingClientRect()
  const x = e.touches[0].clientX - rect.left
  const percentage = (x / rect.width) * 100
  sliderPosition.value = Math.max(0, Math.min(100, percentage))
}
</script>

<template>
  <div 
    class="relative my-8 select-none overflow-hidden rounded-lg border border-border"
    @mousedown="handleMouseDown"
    @mouseup="handleMouseUp"
    @mouseleave="handleMouseUp"
    @mousemove="handleMouseMove"
    @touchmove="handleTouchMove"
    @touchstart="isDragging = true"
    @touchend="isDragging = false"
  >
    <!-- After Image (Full) -->
    <img 
      :src="afterSrc" 
      :alt="afterAlt || 'After'" 
      class="w-full h-auto block"
    />
    
    <!-- Before Image (Clipped) -->
    <div 
      class="absolute inset-0 overflow-hidden"
      :style="{ clipPath: `inset(0 ${100 - sliderPosition}% 0 0)` }"
    >
      <img 
        :src="beforeSrc" 
        :alt="beforeAlt || 'Before'" 
        class="w-full h-auto block"
      />
    </div>
    
    <!-- Slider Line -->
    <div 
      class="absolute top-0 bottom-0 w-1 bg-white cursor-ew-resize"
      :style="{ left: `${sliderPosition}%` }"
    >
      <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-8 h-8 bg-white rounded-full shadow-lg flex items-center justify-center">
        <svg class="w-4 h-4 text-black" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 9l4-4 4 4m0 6l-4 4-4-4" />
        </svg>
      </div>
    </div>
    
    <!-- Labels -->
    <div class="absolute top-4 left-4 px-3 py-1 bg-black/70 rounded-full text-xs font-mono text-white backdrop-blur-sm">
      Before
    </div>
    <div class="absolute top-4 right-4 px-3 py-1 bg-black/70 rounded-full text-xs font-mono text-white backdrop-blur-sm">
      After
    </div>
  </div>
</template>
