<script setup lang="ts">
import { products } from '~/composables/useProducts'
const product = products[0]
const quantity = ref(1)
const added = ref(false)
</script>

<template>
  <main class="min-h-screen bg-[#f5f5f5]">
    <MarketplaceHeader />
    <UContainer class="px-4 py-6 sm:px-6">
      <p class="mb-4 text-sm text-gray-500">Beranda / Elektronik / {{ product.name }}</p>
      <section class="grid gap-6 bg-white p-5 lg:grid-cols-5">
        <div :class="`aspect-square overflow-hidden bg-gradient-to-br ${product.color} text-white lg:col-span-2`"><img :src="product.image" :alt="product.name" class="size-full object-cover" /></div>
        <div class="lg:col-span-3"><h1 class="text-xl text-gray-800 sm:text-2xl">{{ product.name }}</h1><div class="mt-4 flex gap-5 text-sm"><span class="text-orange-500 underline">4.9</span><span class="border-l border-gray-200 pl-5">2,1rb Penilaian</span><span class="border-l border-gray-200 pl-5">{{ product.sold }} Terjual</span></div><div class="mt-6 bg-orange-50 px-5 py-4"><span class="text-3xl font-medium text-orange-500">{{ product.price }}</span></div><div class="mt-7 flex items-center gap-5"><span class="text-sm text-gray-500">Kuantitas</span><div class="flex items-center"><UButton icon="i-lucide-minus" color="neutral" variant="outline" size="xs" @click="quantity = Math.max(1, quantity - 1)" /><span class="min-w-10 text-center">{{ quantity }}</span><UButton icon="i-lucide-plus" color="neutral" variant="outline" size="xs" @click="quantity++" /></div><span class="text-sm text-gray-400">Tersisa 99</span></div><div class="mt-8 flex gap-3"><UButton label="Masukkan Keranjang" icon="i-lucide-shopping-cart" variant="soft" size="lg" @click="added = true" /><UButton label="Beli Sekarang" size="lg" to="/cart" /></div><p v-if="added" class="mt-3 text-sm text-green-600">Produk berhasil ditambahkan ke keranjang.</p></div>
      </section>
      <section class="mt-5 bg-white p-6"><h2 class="border-b border-gray-100 pb-4 text-lg font-semibold">Deskripsi Produk</h2><p class="mt-5 leading-7 text-gray-600">Produk berkualitas pilihan dengan pengiriman cepat dan layanan toko yang terpercaya. Detail produk dapat disesuaikan oleh seller.</p></section>
    </UContainer>
    <MarketplaceFooter />
  </main>
</template>
