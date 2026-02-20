<template>
  <div class="min-h-screen">
    <div class="max-w-5xl mx-auto border-x border-border min-h-screen">
      
      <!-- Header -->
      <header class="px-8 sm:px-12 lg:px-16 py-12 sm:py-16 border-b border-border">
        <div class="flex items-center gap-3 mb-8">
          <NuxtLink 
            to="/blog" 
            class="text-content-muted hover:text-accent transition-colors"
          >
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 19l-7-7m0 0l7-7m-7 7h18"/>
            </svg>
          </NuxtLink>
          <p class="font-mono text-xs uppercase tracking-widest text-content-muted">// {{ formatDate(post.date) }}</p>
        </div>

        <h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold tracking-tight mb-6">
          {{ post.title }}
        </h1>

        <p class="text-xl text-content-secondary leading-relaxed mb-8 max-w-3xl">
          {{ post.description }}
        </p>

        <!-- Meta Info -->
        <div class="flex flex-wrap items-center gap-4 text-sm">
          <div class="flex items-center gap-2">
            <span class="text-content-muted">By</span>
            <span class="text-white font-medium">{{ post.author }}</span>
          </div>
          
          <div class="flex flex-wrap gap-2" v-if="post.tags && post.tags.length > 0">
            <NuxtLink
              v-for="tag in post.tags"
              :key="tag"
              :to="`/blog?tag=${tag}`"
              class="px-3 py-1 text-xs font-mono text-content-muted bg-surface-raised hover:bg-surface-overlay rounded-full transition-colors"
            >
              {{ tag }}
            </NuxtLink>
          </div>
        </div>
      </header>

      <!-- Article Content -->
      <article class="px-8 sm:px-12 lg:px-16 py-12">
        <div class="prose prose-invert prose-lg max-w-none
          prose-headings:font-bold prose-headings:tracking-tight
          prose-h1:text-4xl prose-h1:mb-6
          prose-h2:text-3xl prose-h2:mt-12 prose-h2:mb-4 prose-h2:border-b prose-h2:border-border prose-h2:pb-2
          prose-h3:text-2xl prose-h3:mt-8 prose-h3:mb-3
          prose-p:text-content-secondary prose-p:leading-relaxed prose-p:mb-6
          prose-a:text-accent prose-a:no-underline prose-a:font-medium hover:prose-a:underline
          prose-strong:text-white prose-strong:font-semibold
          prose-code:text-accent prose-code:bg-surface-raised prose-code:px-1.5 prose-code:py-0.5 prose-code:rounded prose-code:font-mono prose-code:text-sm prose-code:before:content-[''] prose-code:after:content-['']
          prose-pre:bg-surface-raised prose-pre:border prose-pre:border-border prose-pre:rounded-lg prose-pre:p-4
          prose-ul:text-content-secondary prose-ul:my-6
          prose-ol:text-content-secondary prose-ol:my-6
          prose-li:my-2
          prose-blockquote:border-l-4 prose-blockquote:border-accent prose-blockquote:pl-4 prose-blockquote:italic prose-blockquote:text-content-secondary
          prose-img:rounded-lg prose-img:border prose-img:border-border
          prose-hr:border-border prose-hr:my-12
          prose-table:text-content-secondary
          prose-th:bg-surface-raised prose-th:border prose-th:border-border
          prose-td:border prose-td:border-border
        ">
          <ContentRenderer :value="post" />
        </div>
      </article>

      <!-- Navigation -->
      <nav class="px-8 sm:px-12 lg:px-16 py-12 border-t border-border">
        <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
          <!-- Previous Post -->
          <NuxtLink
            v-if="prev"
            :to="prev._path"
            class="p-6 rounded-xl bg-surface-raised border border-border hover:border-border-hover transition-colors group"
          >
            <p class="text-xs font-mono text-content-muted mb-2">← Previous</p>
            <p class="font-semibold group-hover:text-accent transition-colors">
              {{ prev.title }}
            </p>
          </NuxtLink>
          <div v-else></div>

          <!-- Next Post -->
          <NuxtLink
            v-if="next"
            :to="next._path"
            class="p-6 rounded-xl bg-surface-raised border border-border hover:border-border-hover transition-colors group text-right"
          >
            <p class="text-xs font-mono text-content-muted mb-2">Next →</p>
            <p class="font-semibold group-hover:text-accent transition-colors">
              {{ next.title }}
            </p>
          </NuxtLink>
        </div>
      </nav>

      <!-- Footer -->
      <footer class="px-8 sm:px-12 lg:px-16 py-10 border-t border-border text-center">
        <p class="font-mono text-xs text-content-muted">¯\_(ツ)_/¯</p>
      </footer>

    </div>
  </div>
</template>

<script setup lang="ts">
const route = useRoute()
const slug = route.params.slug as string

// Fetch the current post
const { data: post } = await useAsyncData(`blog-${slug}`, () => {
  return queryCollection('blog')
    .path(`/blog/${slug}`)
    .first()
})

// Handle 404
if (!post.value) {
  throw createError({
    statusCode: 404,
    statusMessage: 'Post not found'
  })
}

// Fetch surrounding posts for navigation
const { data: surround } = await useAsyncData(`blog-${slug}-surround`, () => {
  return queryCollectionItemSurroundings('blog', post.value!._id)
})

const prev = computed(() => surround.value?.[0])
const next = computed(() => surround.value?.[1])

const formatDate = (date: string) => {
  if (!date) return ''
  return new Date(date).toLocaleDateString('en-GB', {
    day: 'numeric',
    month: 'short',
    year: 'numeric'
  }).toLowerCase()
}

// SEO
useHead({
  title: `${post.value.title} - Ted Mundy`,
  meta: [
    { name: 'description', content: post.value.description },
    { property: 'og:title', content: post.value.title },
    { property: 'og:description', content: post.value.description },
    { property: 'og:type', content: 'article' },
    { property: 'article:published_time', content: post.value.date },
    { property: 'article:author', content: post.value.author },
  ]
})
</script>
