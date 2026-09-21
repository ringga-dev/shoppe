<script setup lang="ts">
const storeName = ref('BisnisKu Store')
const storeDescription = ref('Toko pilihan dengan produk berkualitas.')
const phone = ref('')
const address = ref('')
</script>

<template>
  <main class="min-h-screen bg-[#f5f5f5] lg:flex">
    <DashboardSidebar />
    <section class="min-w-0 flex-1">
      <header class="bg-white px-5 py-4 shadow-sm sm:px-8"><p class="text-sm text-gray-500">Toko Saya</p><h1 class="text-xl font-bold text-gray-800">Pengaturan toko</h1></header>
      <UContainer class="max-w-4xl px-5 py-6 sm:px-8">
        <UCard class="rounded-sm">
          <div class="flex items-center gap-4 border-b border-gray-100 pb-5"><div class="flex size-16 items-center justify-center rounded-full bg-orange-100 text-2xl font-bold text-orange-500">B</div><div><h2 class="font-semibold text-gray-800">{{ storeName }}</h2><p class="text-sm text-gray-500">Atur informasi yang dilihat pembeli</p></div><UButton label="Ganti foto" color="neutral" variant="outline" class="ml-auto" /></div>
          <form class="mt-6 space-y-5" @submit.prevent>
            <UFormField label="Nama toko" required><UInput v-model="storeName" class="w-full" /></UFormField>
            <UFormField label="Deskripsi toko"><UTextarea v-model="storeDescription" class="w-full" /></UFormField>
            <UFormField label="Nomor telepon"><UInput v-model="phone" type="tel" class="w-full" placeholder="+62 812 3456 7890" /></UFormField>
            <UFormField label="Alamat toko"><UTextarea v-model="address" class="w-full" placeholder="Alamat lengkap toko" /></UFormField>
            <div class="flex justify-end border-t border-gray-100 pt-5"><UButton label="Simpan perubahan" type="submit" /></div>
          </form>
        </UCard>
      </UContainer>
    </section>
  </main>
</template>
