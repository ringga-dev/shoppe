<template>
  <header class="border-b border-gray-100 bg-white">
    <UContainer class="flex h-20 items-center justify-between px-4 sm:px-6">
      <NuxtLink to="/" class="flex items-center gap-2 text-2xl font-medium text-[#ee4d2d]">
        <span class="flex size-10 items-center justify-center rounded-lg border-2 border-[#ee4d2d] text-2xl">B</span>
        BisnisKu
      </NuxtLink>
      <div class="flex items-center gap-2 text-sm text-gray-600">
        <span>{{ prompt }}</span>
        <NuxtLink :to="link" class="text-[#ee4d2d] hover:text-[#d94427]">{{ linkLabel }}</NuxtLink>
      </div>
    </UContainer>
  </header>
</template>

<script setup lang="ts">
defineProps<{
  prompt: string
  link: string
  linkLabel: string
}>()
</script>
