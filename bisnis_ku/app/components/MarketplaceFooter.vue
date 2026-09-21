<template>
  <footer class="border-t border-orange-100 bg-white text-xs text-gray-500">
    <UContainer class="grid gap-8 px-4 py-10 sm:grid-cols-2 lg:grid-cols-5 sm:px-6">
      <div><h3 class="font-semibold uppercase text-gray-800">Layanan pelanggan</h3><p class="mt-4 space-y-2">Pusat bantuan<br>Metode pembayaran<br>Pengembalian barang<br>Hubungi kami</p></div>
      <div><h3 class="font-semibold uppercase text-gray-800">Tentang BisnisKu</h3><p class="mt-4">Tentang kami<br>Karier<br>Kebijakan privasi<br>Blog</p></div>
      <div><h3 class="font-semibold uppercase text-gray-800">Ikuti kami</h3><p class="mt-4">Instagram<br>Facebook<br>TikTok<br>YouTube</p></div>
      <div><h3 class="font-semibold uppercase text-gray-800">Download aplikasi</h3><div class="mt-4 flex size-20 items-center justify-center border border-gray-200 text-center text-[10px]">QR CODE</div></div>
      <div><h3 class="font-semibold uppercase text-gray-800">Pembayaran</h3><div class="mt-4 flex flex-wrap gap-2"><UBadge v-for="item in ['VISA', 'DANA', 'OVO', 'QRIS']" :key="item" :label="item" color="neutral" variant="outline" /></div></div>
    </UContainer>
    <div class="border-t border-gray-100 py-5 text-center">© 2026 BisnisKu. Semua hak dilindungi.</div>
  </footer>
</template>
