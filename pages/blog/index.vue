<template>
  <div class="min-h-screen">
    <div class="max-w-5xl mx-auto border-x border-border min-h-screen">
      
      <!-- Header -->
      <header class="px-8 sm:px-12 lg:px-16 py-16 sm:py-20 border-b border-border">
        <div class="flex items-center gap-3 mb-6">
          <NuxtLink 
            to="/" 
            class="text-content-muted hover:text-accent transition-colors"
          >
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 19l-7-7m0 0l7-7m-7 7h18"/>
            </svg>
          </NuxtLink>
          <p class="font-mono text-xs uppercase tracking-widest text-content-muted">// writing</p>
        </div>
        <h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold tracking-tight mb-4">
          Blog
        </h1>
        <p class="text-content-secondary text-lg leading-relaxed max-w-2xl">
          Thoughts on engineering and a few other bits. 
          {{ posts?.length || 0 }} {{ (posts?.length || 0) === 1 ? 'post' : 'posts' }} and counting.
        </p>
      </header>

      <!-- Blog Posts -->
      <section class="px-8 sm:px-12 lg:px-16 py-12">
        <div class="space-y-6">
          <NuxtLink
            v-for="post in (posts || [])"
            :key="post.path"
            :to="post.path"
            class="block p-6 sm:p-8 rounded-2xl bg-surface-raised border border-border hover:border-border-hover transition-all group"
          >
            <!-- Date -->
            <div class="mb-3">
              <span class="font-mono text-xs text-content-muted">
                {{ formatDate(post.date) }}
              </span>
            </div>

            <!-- Title -->
            <h2 class="text-2xl sm:text-3xl font-semibold mb-3 group-hover:text-accent transition-colors">
              {{ post.title }}
            </h2>

            <!-- Description -->
            <p class="text-content-secondary leading-relaxed mb-4">
              {{ post.description }}
            </p>

            <!-- Read More -->
            <div class="flex items-center gap-2 text-sm text-accent font-medium">
              <span>Read more</span>
              <svg class="w-4 h-4 group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/>
              </svg>
            </div>
          </NuxtLink>
        </div>
      </section>

      <!-- Footer -->
      <footer class="px-8 sm:px-12 lg:px-16 py-10 border-t border-border text-center">
        <p class="font-mono text-xs text-content-muted">¯\_(ツ)_/¯</p>
      </footer>

    </div>
  </div>
</template>

<script setup lang="ts">
// Fetch all blog posts using the new collection API
const { data: posts } = await useAsyncData('blog-posts', () => {
  return queryCollection('blog')
    .where('draft', '=', false)
    .order('date', 'DESC')
    .all()
})

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
  title: 'Blog - Ted Mundy',
  meta: [
    { 
      name: 'description', 
      content: 'Thoughts on engineering and a few other bits.' 
    }
  ]
})
</script>
