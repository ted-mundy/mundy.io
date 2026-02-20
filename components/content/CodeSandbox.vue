<script setup lang="ts">
const props = defineProps<{
  id: string
  title?: string
  height?: string
}>()

const sandboxUrl = computed(() => 
  `https://codesandbox.io/embed/${props.id}?fontsize=14&hidenavigation=1&theme=dark`
)
</script>

<template>
  <div class="my-8 rounded-lg overflow-hidden border border-border bg-surface-raised">
    <div v-if="title" class="px-4 py-2 border-b border-border bg-surface-overlay">
      <p class="text-sm font-mono text-content-muted">{{ title }}</p>
    </div>
    <iframe
      :src="sandboxUrl"
      :style="{ height: height || '500px' }"
      class="w-full border-0"
      :title="`CodeSandbox: ${title || id}`"
      allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
      sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
    />
  </div>
</template>
