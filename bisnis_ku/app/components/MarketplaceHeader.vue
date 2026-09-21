<template>
  <header class="bg-gradient-to-b from-[#ee4d2d] to-[#ff7337] text-white">
    <UContainer class="px-4 sm:px-5">
      <div class="flex h-10 items-center justify-end gap-4 text-sm">
        <button class="flex items-center gap-1"><UIcon name="i-lucide-globe-2" /> Language <UIcon name="i-lucide-chevron-down" /></button>
        <NuxtLink to="/auth/register">Sign Up</NuxtLink>
        <span class="h-4 border-l border-white/50" />
        <NuxtLink to="/auth/login">Login</NuxtLink>
      </div>
      <div class="flex items-center gap-5 pb-5 pt-3">
        <NuxtLink to="/" class="flex shrink-0 items-center gap-2 text-xl font-medium sm:text-2xl">
          <img src="/reference/images/shopee-icon.svg" alt="" class="size-9 brightness-0 invert sm:size-11" />
          <span>BisnisKu</span>
        </NuxtLink>
        <div class="flex flex-1 rounded-sm bg-white p-1">
          <input class="min-w-0 flex-1 px-4 py-2 text-sm text-gray-700 outline-none sm:text-base" placeholder="Search for products, brands and shops..." />
          <UButton icon="i-lucide-search" class="rounded-sm bg-[#ee4d2d] text-white hover:bg-[#d94427]" aria-label="Search" />
        </div>
        <NuxtLink to="/cart" class="hidden sm:block"><UIcon name="i-lucide-shopping-cart" class="size-8" /></NuxtLink>
      </div>
    </UContainer>
  </header>
</template>
