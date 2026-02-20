<template>
  <div class="min-h-screen">
    <!-- Main Container with side borders -->
    <div class="max-w-5xl mx-auto border-x border-border min-h-screen">

      <!-- Hero Section -->
      <header class="px-8 sm:px-12 lg:px-16 py-20 sm:py-28 lg:py-36">
        <div class="flex flex-col lg:flex-row lg:items-center lg:justify-between gap-12">
          <div class="flex-1">
            <p class="font-mono text-xs uppercase tracking-widest text-accent mb-6">// about</p>
            <h1 class="text-5xl sm:text-6xl lg:text-7xl font-bold tracking-tight mb-6">
              ted mundy
            </h1>
            <p class="text-2xl sm:text-3xl text-content-secondary font-medium mb-8">
              software engineer
            </p>
            <p class="text-content-secondary text-lg leading-relaxed max-w-xl mb-10">
              Self-taught since age 9. Building & scaling applications, currently at <a href="https://zahnapp.com" target="_blank" rel="noopener" class="link-accent font-medium">ZAHN</a>.
            </p>

            <!-- Contact Links -->
            <div class="flex flex-wrap gap-3">
              <a
                href="mailto:ted@mundy.io"
                class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-white text-surface font-medium text-sm hover:bg-white/90 transition-colors"
              >
                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
                </svg>
                Get in touch
              </a>
              <a
                href="/cv.pdf"
                target="_blank"
                rel="noopener"
                class="inline-flex items-center gap-2 px-4 py-2 rounded-full border border-border text-content-secondary font-medium text-sm hover:border-border-hover hover:text-content transition-colors"
              >
                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"/>
                </svg>
                CV
              </a>
              <a
                href="https://github.com/ted-mundy"
                target="_blank"
                rel="noopener"
                class="inline-flex items-center gap-2 px-4 py-2 rounded-full border border-border text-content-secondary font-medium text-sm hover:border-border-hover hover:text-content transition-colors"
              >
                <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                </svg>
                GitHub
              </a>
            </div>
          </div>

          <!-- Globe gradient -->
          <div class="hidden lg:block relative w-64 h-64 shrink-0">
            <div class="absolute inset-0 rounded-full bg-gradient-to-br from-accent/20 to-transparent"></div>
          </div>
        </div>
      </header>

      <hr class="border-border" />

      <!-- Projects Section -->
      <section class="px-8 sm:px-12 lg:px-16 py-16 sm:py-20">
        <p class="font-mono text-xs uppercase tracking-widest text-content-muted mb-10">// projects</p>

        <!-- ClipHog - Featured Project -->
        <a href="https://cliphog.com" target="_blank" rel="noopener" class="block p-8 rounded-2xl bg-surface-raised border border-border hover:border-border-hover transition-colors group">
          <div class="flex items-start justify-between mb-4">
            <div>
              <span class="inline-block px-2 py-1 text-xs font-mono text-accent bg-accent/10 rounded mb-3">founder</span>
              <h3 class="text-2xl font-semibold group-hover:text-accent transition-colors">
                ClipHog
              </h3>
            </div>
            <svg class="w-5 h-5 text-content-muted group-hover:text-accent transition-colors" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"/>
            </svg>
          </div>
          <p class="text-content-secondary leading-relaxed mb-6 max-w-2xl">
            Solo-founded a shorts generation platform that leverages LLM and video understanding models to automatically create short-form content from long-form videos. Owned the entire project lifecycle from ideation to deployment.
          </p>

          <!-- Stats -->
          <div class="flex flex-wrap gap-6 mb-6">
            <div>
              <p class="text-2xl font-bold text-white tabular-nums"><span class="counter" data-target="6000" data-suffix="+">0,000+</span></p>
              <p class="text-xs text-content-muted font-mono">videos generated</p>
            </div>
            <div>
              <p class="text-2xl font-bold text-white tabular-nums"><span class="counter" data-target="3000" data-suffix="+">0,000+</span></p>
              <p class="text-xs text-content-muted font-mono">users</p>
            </div>
            <div>
              <p class="text-2xl font-bold text-white tabular-nums"><span class="counter" data-target="1600" data-suffix="">0,000</span></p>
              <p class="text-xs text-content-muted font-mono">videos/month peak</p>
            </div>
          </div>

          <div class="flex flex-wrap gap-2">
            <span class="px-3 py-1 text-xs font-mono text-content-muted bg-surface-overlay rounded-full">ai/ml</span>
            <span class="px-3 py-1 text-xs font-mono text-content-muted bg-surface-overlay rounded-full">video processing</span>
            <span class="px-3 py-1 text-xs font-mono text-content-muted bg-surface-overlay rounded-full">saas</span>
          </div>
        </a>
      </section>

      <hr class="border-border" />

      <!-- Writing Section -->
      <section class="px-8 sm:px-12 lg:px-16 py-16 sm:py-20">
        <div class="flex items-center justify-between mb-10">
          <p class="font-mono text-xs uppercase tracking-widest text-content-muted">// writing</p>
          <a href="/blog" class="text-sm text-content-secondary hover:text-accent transition-colors">
            View all &rarr;
          </a>
        </div>

        <div class="space-y-4">
          <NuxtLink
            v-for="post in (recentPosts || [])"
            :key="post.path"
            :to="post.path"
            class="block p-6 rounded-xl bg-surface-raised border border-border hover:border-border-hover transition-colors group"
          >
            <div class="flex flex-col sm:flex-row sm:items-center sm:justify-between gap-2 mb-2">
              <h4 class="font-semibold group-hover:text-accent transition-colors">{{ post.title }}</h4>
              <span class="font-mono text-xs text-content-muted shrink-0">{{ formatDate(post.date) }}</span>
            </div>
            <p class="text-content-secondary text-sm leading-relaxed">{{ post.description }}</p>
          </NuxtLink>
        </div>
      </section>

      <hr class="border-border" />

      <!-- Experience Section -->
      <section class="px-8 sm:px-12 lg:px-16 py-16 sm:py-20">
        <p class="font-mono text-xs uppercase tracking-widest text-content-muted mb-10">// experience</p>

        <div class="space-y-8">
          <!-- Current Role -->
          <div class="relative pl-6 border-l-2 border-accent">
            <div class="absolute -left-[9px] top-1 w-4 h-4 rounded-full bg-accent"></div>
            <div class="flex flex-col sm:flex-row sm:items-start sm:justify-between gap-2 mb-3">
              <div>
                <h4 class="text-xl font-semibold">Software Engineer</h4>
                <a href="https://zahnapp.com" target="_blank" rel="noopener" class="link-accent">ZAHN</a>
              </div>
              <span class="font-mono text-sm text-accent shrink-0">2025 — present</span>
            </div>
            <p class="text-content-secondary leading-relaxed">
              Early hire building safety-oriented app for people living in cities.
            </p>
          </div>

          <!-- Past Role -->
          <div class="relative pl-6 border-l-2 border-border">
                        <div class="flex flex-col sm:flex-row sm:items-start sm:justify-between gap-2 mb-3">
              <div>
                <h4 class="text-lg font-semibold">Junior Software Engineer</h4>
                <a href="https://pagesuite.com" target="_blank" rel="noopener" class="link-accent text-sm">PageSuite</a>
              </div>
              <span class="font-mono text-sm text-content-muted shrink-0">2024 — 2025</span>
            </div>
            <p class="text-content-secondary text-sm leading-relaxed">
              Maintained and enhanced a SaaS platform for digital publishers. Managed a team of 3 developers and led code reviews.
            </p>
          </div>

          <!-- Past Role -->
          <div class="relative pl-6 border-l-2 border-border">
                        <div class="flex flex-col sm:flex-row sm:items-start sm:justify-between gap-2 mb-3">
              <div>
                <h4 class="text-lg font-semibold">Software Developer</h4>
                <a href="https://acris.co.uk" target="_blank" rel="noopener" class="link-accent text-sm">Acris</a>
              </div>
              <span class="font-mono text-sm text-content-muted shrink-0">2022 — 2024</span>
            </div>
            <p class="text-content-secondary text-sm leading-relaxed">
              Completed apprenticeship and led development of greenfield platforms for real-time business delivery tracking.
            </p>
          </div>
        </div>
      </section>

      <hr class="border-border" />

      <!-- Footer -->
      <footer class="px-8 sm:px-12 lg:px-16 py-10 text-center">
        <p class="font-mono text-xs text-content-muted">¯\_(ツ)_/¯</p>
      </footer>

    </div>
  </div>
</template>

<script setup>
// Fetch recent blog posts using collection API
const { data: recentPosts } = await useAsyncData('recent-posts', () => {
  return queryCollection('blog')
    .where('draft', '=', false)
    .order('date', 'DESC')
    .limit(2)
    .all()
})

onMounted(() => {
  const counters = document.querySelectorAll('.counter')

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const counter = entry.target
        const target = parseInt(counter.dataset.target)
        const suffix = counter.dataset.suffix || ''
        const duration = 2000
        const start = performance.now()
        const targetDigits = target.toString().length

        // Pad number with leading zeros to match target length
        const formatWithZeros = (num) => {
          const padded = num.toString().padStart(targetDigits, '0')
          // Add commas in the right places
          return padded.replace(/\B(?=(\d{3})+(?!\d))/g, ',')
        }

        const animate = (currentTime) => {
          const elapsed = currentTime - start
          const progress = Math.min(elapsed / duration, 1)

          // Ease-in-out for smooth acceleration and deceleration
          const easeInOut = progress < 0.5
            ? 4 * progress * progress * progress
            : 1 - Math.pow(-2 * progress + 2, 3) / 2
          const current = Math.floor(easeInOut * target)

          counter.textContent = formatWithZeros(current) + suffix

          // Motion blur effect using text-shadow
          const intensity = (1 - progress)
          const offset = intensity * 8
          counter.style.textShadow = `
            0 ${offset * 0.25}px 0 rgba(161, 161, 170, ${intensity * 0.3}),
            0 ${offset * 0.5}px 0 rgba(161, 161, 170, ${intensity * 0.2}),
            0 ${offset}px 0 rgba(161, 161, 170, ${intensity * 0.1}),
            0 ${-offset * 0.25}px 0 rgba(161, 161, 170, ${intensity * 0.3}),
            0 ${-offset * 0.5}px 0 rgba(161, 161, 170, ${intensity * 0.2}),
            0 ${-offset}px 0 rgba(161, 161, 170, ${intensity * 0.1})
          `

          if (progress < 1) {
            requestAnimationFrame(animate)
          }
        }

        requestAnimationFrame(animate)
        observer.unobserve(counter)
      }
    })
  }, { threshold: 0.5 })

  counters.forEach(counter => observer.observe(counter))
})

const formatDate = (date) => {
  if (!date) return ''
  return new Date(date).toLocaleDateString('en-GB', {
    month: 'short',
    year: 'numeric'
  }).toLowerCase()
}
</script>
