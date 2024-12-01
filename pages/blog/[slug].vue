<template>
  <ContentDoc :path="$route.params.slug">
    <!-- not-found -->
    <template #not-found>
      <!-- <div class="text-center mx-auto max-w-3xl px-4">
        <h1 class="font-bold text-4xl mt-20">
          nothing here
        </h1>
        <p class="mt-2 font-bold">
          you should go back to the <a href="/">home page.</a>
        </p>
      </div> -->
      <NuxtLayout name="not-found" />
    </template>
  </ContentDoc>
</template>
