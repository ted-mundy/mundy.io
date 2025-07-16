<template>
  <div class="sticky top-0 z-50 w-screen bg-white border-b">
    <div class="px-4">
      <nav class="flex items-center justify-between gap-4 py-4">
        <div class="flex items-center gap-4">
          <NuxtLink to="/">about me</NuxtLink>
        </div>
        <div class="flex items-center gap-4">
          <a href="https://github.com/ted-mundy/">github</a>
          <a href="mailto:ted@mundy.io">email me! (ted@mundy.io)</a>
        </div>
      </nav>
    </div>
  </div>
  <div class="content max-w-3xl mx-auto mt-16 flex flex-col">
    <h1 class="text-5xl mb-6 font-bold">
      blog
    </h1>
    <p class="mb-6">
      this is the blog ... if you're <i>really</i> bored, you can read any of my posts below.
    </p>
    <ul class="list-disc pl-6">
      <li class="mb-2">
        <NuxtLink to="/blog/cliphog">cliphog</NuxtLink>
      </li>
    </ul>
  </div>
</template>
