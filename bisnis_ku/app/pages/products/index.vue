<script setup lang="ts">
import { products } from '~/composables/useProducts'
const categories = ['Elektronik', 'Fashion Pria', 'Fashion Wanita', 'Kesehatan', 'Rumah Tangga', 'Makanan']
</script>

<template>
  <main class="min-h-screen bg-[#f5f5f5]">
    <MarketplaceHeader />
    <UContainer class="grid gap-5 px-4 py-6 lg:grid-cols-12 sm:px-6">
      <aside class="bg-white p-5 lg:col-span-3">
        <h2 class="flex items-center gap-2 font-semibold text-gray-800"><UIcon name="i-lucide-list-filter" /> Filter pencarian</h2>
        <div class="mt-6 border-b border-gray-100 pb-5"><p class="font-medium text-gray-700">Kategori</p><div class="mt-4 space-y-3 text-sm text-gray-600"><label v-for="category in categories" :key="category" class="flex items-center gap-2"><input type="checkbox" class="accent-orange-500"> {{ category }}</label></div></div>
        <div class="mt-5 border-b border-gray-100 pb-5"><p class="font-medium text-gray-700">Rentang harga</p><div class="mt-3 flex gap-2"><UInput placeholder="Rp Dari" size="sm" /><UInput placeholder="Rp Sampai" size="sm" /></div></div>
        <UButton label="Terapkan" block class="mt-5" />
      </aside>
      <section class="lg:col-span-9">
        <div class="mb-4 bg-white p-4"><p class="text-sm text-gray-500">Beranda / Semua produk</p><h1 class="mt-2 text-xl font-semibold text-gray-800">Semua Produk</h1></div>
        <div class="mb-4 flex flex-wrap items-center gap-2 bg-white p-3"><span class="mr-2 text-sm text-gray-500">Urutkan menurut</span><UButton label="Relevansi" color="primary" variant="soft" size="sm" /><UButton label="Terbaru" color="neutral" variant="ghost" size="sm" /><UButton label="Terlaris" color="neutral" variant="ghost" size="sm" /><UButton label="Harga" color="neutral" variant="ghost" size="sm" /></div>
        <div class="grid grid-cols-2 gap-3 sm:grid-cols-3 lg:grid-cols-4">
          <ProductCard v-for="product in products" :key="product.name" :product="product" />
        </div>
        <div class="flex justify-center gap-1 py-8"><UButton label="1" /><UButton label="2" color="neutral" variant="ghost" /><UButton label="3" color="neutral" variant="ghost" /><UButton icon="i-lucide-chevron-right" color="neutral" variant="ghost" /></div>
      </section>
    </UContainer>
    <MarketplaceFooter />
  </main>
</template>
