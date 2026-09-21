<template>
  <aside class="w-full shrink-0 border-b border-gray-200 bg-white lg:w-60 lg:border-b-0 lg:border-r">
    <div class="flex items-center gap-2 border-b border-gray-100 px-5 py-5 text-xl font-black text-orange-500"><span class="flex size-8 items-center justify-center rounded bg-orange-500 text-sm text-white">B</span> BisnisKu</div>
    <nav class="grid grid-cols-3 gap-1 p-3 lg:block lg:space-y-1">
      <NuxtLink to="/dashboard" class="flex items-center gap-3 rounded px-3 py-2 text-sm text-gray-600 hover:bg-orange-50 hover:text-orange-500"><UIcon name="i-lucide-layout-dashboard" /> Dashboard</NuxtLink>
      <NuxtLink to="/dashboard" class="flex items-center gap-3 rounded px-3 py-2 text-sm text-gray-600 hover:bg-orange-50 hover:text-orange-500"><UIcon name="i-lucide-package" /> Produk</NuxtLink>
      <NuxtLink to="/dashboard" class="flex items-center gap-3 rounded px-3 py-2 text-sm text-gray-600 hover:bg-orange-50 hover:text-orange-500"><UIcon name="i-lucide-shopping-bag" /> Pesanan</NuxtLink>
      <NuxtLink to="/dashboard/setting/toko" class="flex items-center gap-3 rounded px-3 py-2 text-sm text-gray-600 hover:bg-orange-50 hover:text-orange-500"><UIcon name="i-lucide-store" /> Pengaturan toko</NuxtLink>
    </nav>
  </aside>
</template>
