<script setup lang="ts">
const props = defineProps<{
  id: string
  theme?: 'light' | 'dark'
}>()

const tweetUrl = computed(() => `https://platform.twitter.com/embed/Tweet.html?id=${props.id}&theme=${props.theme || 'dark'}`)
</script>

<template>
  <div class="my-8 flex justify-center">
    <div class="w-full max-w-xl">
      <iframe
        :src="tweetUrl"
        class="w-full border-0 rounded-lg"
        style="height: 500px;"
        :title="`Tweet ${id}`"
      />
    </div>
  </div>
</template>
