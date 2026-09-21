<script setup lang="ts">
const stats = [
  { label: 'Total penjualan', value: 'Rp 12.450.000', icon: 'i-lucide-wallet', color: 'text-orange-500 bg-orange-50' },
  { label: 'Pesanan baru', value: '128', icon: 'i-lucide-shopping-bag', color: 'text-blue-500 bg-blue-50' },
  { label: 'Produk aktif', value: '46', icon: 'i-lucide-package', color: 'text-green-500 bg-green-50' }
]
</script>

<template>
  <main class="min-h-screen bg-[#f5f5f5] lg:flex">
    <DashboardSidebar />
    <section class="min-w-0 flex-1">
      <header class="flex items-center justify-between bg-white px-5 py-4 shadow-sm sm:px-8">
        <div><p class="text-sm text-gray-500">Selamat datang kembali, Seller</p><h1 class="text-xl font-bold text-gray-800">Ringkasan toko</h1></div>
        <UButton icon="i-lucide-bell" color="neutral" variant="ghost" aria-label="Notifikasi" />
      </header>
      <UContainer class="px-5 py-6 sm:px-8">
        <div class="grid gap-4 md:grid-cols-3">
          <UCard v-for="stat in stats" :key="stat.label" class="rounded-sm">
            <div class="flex items-start justify-between"><div><p class="text-sm text-gray-500">{{ stat.label }}</p><p class="mt-2 text-2xl font-bold text-gray-800">{{ stat.value }}</p></div><div :class="`rounded-lg p-3 ${stat.color}`"><UIcon :name="stat.icon" class="size-5" /></div></div>
            <p class="mt-4 text-xs text-green-600">↑ 12,5% dari bulan lalu</p>
          </UCard>
        </div>
        <div class="mt-5 grid gap-5 lg:grid-cols-2">
          <UCard class="rounded-sm"><div class="flex justify-between"><h2 class="font-semibold text-gray-800">Pesanan terbaru</h2><UButton label="Lihat semua" variant="link" size="sm" /></div><p class="py-12 text-center text-sm text-gray-500">Belum ada pesanan baru</p></UCard>
          <UCard class="rounded-sm"><div class="flex justify-between"><h2 class="font-semibold text-gray-800">Produk terlaris</h2><UButton label="Kelola produk" variant="link" size="sm" /></div><p class="py-12 text-center text-sm text-gray-500">Tambahkan produk untuk melihat data</p></UCard>
        </div>
      </UContainer>
    </section>
  </main>
</template>
