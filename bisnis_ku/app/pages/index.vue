<script setup lang="ts">
import { products } from '~/composables/useProducts'

const slides = ['/reference/slider/img1.png', '/reference/slider/img2.jpg', '/reference/slider/img5.jpg', '/reference/slider/img6.png']
const slideIndex = ref(0)
const categories = [
  ['Elektronik', 'i-lucide-monitor'], ['Komputer & Aksesoris', 'i-lucide-laptop'], ['Handphone & Aksesoris', 'i-lucide-smartphone'],
  ['Pakaian Pria', 'i-lucide-shirt'], ['Sepatu Pria', 'i-lucide-footprints'], ['Tas Pria', 'i-lucide-backpack'],
  ['Aksesori Fashion', 'i-lucide-glasses'], ['Jam Tangan', 'i-lucide-watch'], ['Kesehatan', 'i-lucide-heart-pulse'],
  ['Hobi & Koleksi', 'i-lucide-guitar'], ['Makanan & Minuman', 'i-lucide-utensils'], ['Perawatan & Kecantikan', 'i-lucide-sparkles'],
  ['Perlengkapan Rumah', 'i-lucide-house'], ['Pakaian Wanita', 'i-lucide-dress'], ['Fashion Muslim', 'i-lucide-user-round'],
  ['Fashion Bayi & Anak', 'i-lucide-baby'], ['Ibu & Bayi', 'i-lucide-baby'], ['Sepatu Wanita', 'i-lucide-footprints'],
  ['Tas Wanita', 'i-lucide-handbag'], ['Otomotif', 'i-lucide-car']
]
const services = [
  ['Shopee Pilih Lokal', 'i-lucide-heart-handshake', 'text-red-500'], ['Shopee Mall', 'i-lucide-shopping-bag', 'text-red-600'],
  ['Pulsa & Tagihan', 'i-lucide-smartphone', 'text-emerald-500'], ['Flash Sale', 'i-lucide-percent', 'text-orange-500'],
  ['Shopee Supermarket', 'i-lucide-store', 'text-blue-500'], ['Dikelola Shopee', 'i-lucide-warehouse', 'text-red-500'],
  ['FitCheck Diskon 25%', 'i-lucide-shirt', 'text-orange-500'], ['Gratis Ongkir dan Voucher', 'i-lucide-ticket', 'text-yellow-500'],
  ['Shopee Barokah', 'i-lucide-moon-star', 'text-teal-500'], ['Semua Promo', 'i-lucide-tags', 'text-green-500']
]
const flashProducts = products.slice(0, 6)
const topProducts = products.slice(3, 9)
let timer: ReturnType<typeof setInterval> | undefined

onMounted(() => {
  timer = setInterval(() => { slideIndex.value = (slideIndex.value + 1) % slides.length }, 5000)
})
onBeforeUnmount(() => { if (timer) clearInterval(timer) })
</script>

<template>
  <main class="min-h-screen bg-[#f5f5f5] font-sans">
    <MarketplaceHeader />
    <UContainer class="px-0 sm:px-4">
      <section class="grid gap-1 bg-white py-5 md:grid-cols-3">
        <div class="relative overflow-hidden md:col-span-2">
          <img :src="slides[slideIndex]" alt="Promo BisnisKu" class="aspect-[2/1] h-full w-full object-cover">
          <div class="absolute bottom-3 left-0 right-0 flex justify-center gap-2">
            <button v-for="(_, index) in slides" :key="index" class="size-2 rounded-full border border-white" :class="index === slideIndex ? 'bg-orange-500' : 'bg-white'" @click="slideIndex = index" />
          </div>
        </div>
        <div class="grid gap-1">
          <img src="/reference/slider/img3.jpg" alt="Promo toko" class="h-full min-h-28 w-full object-cover">
          <img src="/reference/slider/img4.png" alt="Promo voucher" class="h-full min-h-28 w-full object-cover">
        </div>
      </section>

      <section class="grid grid-cols-5 gap-y-5 bg-white px-3 py-5 sm:grid-cols-10">
        <NuxtLink v-for="service in services" :key="service[0]" to="/products" class="group text-center text-[10px] text-gray-700 sm:text-xs">
          <div class="mx-auto flex size-11 items-center justify-center rounded-full border border-gray-100 bg-white shadow-sm transition group-hover:-translate-y-1"><UIcon :name="service[1]" :class="`size-6 ${service[2]}`" /></div>
          <p class="mx-auto mt-2 max-w-20 leading-3">{{ service[0] }}</p>
        </NuxtLink>
      </section>

      <section class="mt-4 bg-white">
        <div class="border-b border-gray-100 px-4 py-4 text-sm uppercase text-gray-500">Kategori</div>
        <div class="grid grid-cols-5 border-l border-t border-gray-100 sm:grid-cols-10">
          <NuxtLink v-for="category in categories" :key="category[0]" to="/products" class="flex min-h-28 flex-col items-center justify-center gap-3 border-b border-r border-gray-100 px-1 text-center text-[10px] text-gray-700 transition hover:text-orange-500 sm:text-xs">
            <div class="flex size-12 items-center justify-center rounded-full bg-gray-50"><UIcon :name="category[1]" class="size-7 text-gray-500" /></div>
            <span>{{ category[0] }}</span>
          </NuxtLink>
        </div>
      </section>

      <section class="mt-4 bg-white">
        <div class="flex items-center justify-between border-b border-gray-100 px-4 py-4">
          <h2 class="flex items-center gap-2 font-semibold uppercase text-orange-500"><UIcon name="i-lucide-flame" /> Flash Sale <UBadge label="00 09 04" color="neutral" variant="solid" /></h2>
          <NuxtLink to="/products" class="text-xs text-orange-500">Lihat Semua ›</NuxtLink>
        </div>
        <div class="grid grid-cols-2 gap-3 p-3 sm:grid-cols-3 md:grid-cols-6">
          <ProductCard v-for="product in flashProducts" :key="product.name" :product="product" />
        </div>
      </section>

      <section class="mt-4 bg-white">
        <div class="flex items-center justify-between border-b border-gray-100 px-4 py-4">
          <h2 class="font-medium uppercase text-orange-500">Produk Terlaris</h2>
          <NuxtLink to="/products" class="text-xs text-orange-500">Lihat Semua ›</NuxtLink>
        </div>
        <div class="grid grid-cols-2 gap-3 p-3 sm:grid-cols-3 md:grid-cols-6">
          <ProductCard v-for="product in topProducts" :key="product.name" :product="product" />
        </div>
      </section>

      <section class="mt-4 bg-white">
        <h2 class="border-b-2 border-orange-500 px-4 py-4 text-center text-sm uppercase text-orange-500">Rekomendasi</h2>
        <div class="grid grid-cols-2 gap-3 p-3 sm:grid-cols-3 md:grid-cols-5">
          <ProductCard v-for="product in products" :key="`recommend-${product.name}`" :product="product" />
        </div>
        <div class="flex justify-center pb-6"><UButton label="Login Untuk Lihat Lainnya" color="neutral" variant="outline" to="/auth/login" /></div>
      </section>

      <section class="mt-4 bg-white px-5 py-8 text-xs leading-5 text-gray-500">
        <h2 class="text-sm font-semibold text-gray-700">BisnisKu Indonesia - Jual Beli Online</h2>
        <p class="mt-3">BisnisKu adalah marketplace lokal yang menyediakan pengalaman belanja online yang mudah, aman, dan terpercaya. Temukan berbagai produk kebutuhan sehari-hari dari seller pilihan di seluruh Indonesia.</p>
        <h3 class="mt-5 font-semibold text-gray-700">Belanja Online Terpercaya di BisnisKu</h3>
        <p class="mt-2">Jelajahi kategori elektronik, fashion, kesehatan, kecantikan, rumah tangga, makanan, hobi, dan masih banyak lagi. Nikmati promo menarik, voucher toko, serta pilihan pengiriman yang nyaman.</p>
        <h3 class="mt-5 font-semibold text-gray-700">Mudah Jualan Online dengan Fitur Lengkap</h3>
        <p class="mt-2">Seller dapat mengelola produk, pesanan, informasi toko, dan penjualan melalui dashboard yang praktis. BisnisKu membantu toko lokal tumbuh dan menjangkau pelanggan lebih luas.</p>
      </section>
    </UContainer>
    <MarketplaceFooter />
  </main>
</template>
