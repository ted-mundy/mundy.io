<script setup lang="ts">
const props = defineProps<{
  src: string
  poster?: string
  caption?: string
}>()
</script>

<template>
  <figure class="my-8">
    <div class="rounded-lg overflow-hidden border border-border bg-black">
      <video
        :src="src"
        :poster="poster"
        controls
        class="w-full"
      >
        Your browser does not support the video tag.
      </video>
    </div>
    <figcaption v-if="caption" class="mt-2 text-sm text-content-muted text-center font-mono">
      {{ caption }}
    </figcaption>
  </figure>
</template>
