<script setup lang="ts">
const selected = ref(true)
const quantity = ref(1)
const product = products[0]
import { products } from '~/composables/useProducts'
</script>

<template>
  <main class="min-h-screen bg-[#f5f5f5]">
    <MarketplaceHeader />
    <UContainer class="px-4 py-8 sm:px-6">
      <div class="mb-4 flex items-center gap-3 bg-white p-5"><UIcon name="i-lucide-shopping-cart" class="size-6 text-orange-500" /><h1 class="text-xl font-semibold text-gray-800">Keranjang Belanja</h1></div>
      <div class="grid gap-5 lg:grid-cols-12">
        <section class="bg-white lg:col-span-8"><div class="flex items-center gap-3 border-b border-gray-100 p-4 text-sm text-gray-500"><UCheckbox v-model="selected" label="Pilih semua" /><span class="ml-auto">Harga satuan</span><span class="w-24 text-center">Kuantitas</span><span class="w-24 text-right">Total harga</span></div><div class="flex gap-4 p-5"><UCheckbox v-model="selected" /><div class="size-24 shrink-0 overflow-hidden"><img :src="product.image" :alt="product.name" class="size-full object-cover" /></div><div class="flex-1"><p class="text-sm text-gray-700">{{ product.name }}</p><p class="mt-2 text-xs text-gray-500">Variasi: Standar</p></div><div class="text-sm text-gray-700">{{ product.price }}</div><div class="flex items-center"><UButton icon="i-lucide-minus" color="neutral" variant="outline" size="xs" @click="quantity = Math.max(1, quantity - 1)" /><span class="min-w-8 text-center text-sm">{{ quantity }}</span><UButton icon="i-lucide-plus" color="neutral" variant="outline" size="xs" @click="quantity++" /></div><div class="w-24 text-right text-sm text-orange-500">{{ product.price }}</div></div></section>
        <aside class="h-fit bg-white p-5 lg:col-span-4"><h2 class="font-semibold text-gray-800">Ringkasan belanja</h2><div class="mt-6 flex justify-between text-sm text-gray-600"><span>Total produk</span><span>{{ product.price }}</span></div><div class="mt-3 flex justify-between text-sm text-gray-600"><span>Biaya pengiriman</span><span>Rp 0</span></div><div class="my-5 border-t border-gray-100 pt-5 flex justify-between"><span>Total pembayaran</span><span class="text-xl text-orange-500">{{ product.price }}</span></div><UButton label="Checkout" block size="lg" to="/dashboard" /></aside>
      </div>
    </UContainer>
    <MarketplaceFooter />
  </main>
</template>
