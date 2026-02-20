<script setup lang="ts">
const props = defineProps<{
  type?: 'info' | 'warning' | 'success' | 'error'
  icon?: string
}>()

const typeStyles = {
  info: 'bg-blue-500/10 border-blue-500/30 text-blue-400',
  warning: 'bg-yellow-500/10 border-yellow-500/30 text-yellow-400',
  success: 'bg-green-500/10 border-green-500/30 text-green-400',
  error: 'bg-red-500/10 border-red-500/30 text-red-400',
}

const icons = {
  info: 'ℹ️',
  warning: '⚠️',
  success: '✅',
  error: '❌',
}

const currentType = props.type || 'info'
</script>

<template>
  <div
    :class="typeStyles[currentType]"
    class="my-6 p-4 rounded-lg border-2 backdrop-blur-sm"
  >
    <div class="flex gap-3">
      <span class="text-xl shrink-0">{{ icon || icons[currentType] }}</span>
      <div class="prose prose-invert prose-sm max-w-none flex-1">
        <slot />
      </div>
    </div>
  </div>
</template>
