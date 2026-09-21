<template>
  <main class="min-h-screen bg-[#f5f5f5]">
    <MarketplaceHeader />
    <UContainer class="grid gap-5 px-4 py-8 lg:grid-cols-4 sm:px-6">
      <aside class="bg-white p-5"><div class="flex items-center gap-3 border-b border-gray-100 pb-5"><div class="flex size-12 items-center justify-center rounded-full bg-orange-100 text-orange-500">U</div><div><p class="font-medium text-gray-800">User BisnisKu</p><p class="text-xs text-gray-500">Edit profil</p></div></div><nav class="mt-5 space-y-3 text-sm"><NuxtLink to="/profile" class="block text-orange-500">Profil saya</NuxtLink><NuxtLink to="/dashboard" class="block text-gray-600">Pesanan saya</NuxtLink><NuxtLink to="/dashboard/setting/toko" class="block text-gray-600">Pengaturan</NuxtLink></nav></aside>
      <section class="bg-white p-6 lg:col-span-3"><h1 class="border-b border-gray-100 pb-5 text-xl font-semibold text-gray-800">Profil saya</h1><p class="mt-2 text-sm text-gray-500">Kelola informasi profil untuk keamanan akun</p><form class="mt-8 max-w-xl space-y-5" @submit.prevent><UFormField label="Nama"><UInput value="User BisnisKu" class="w-full" /></UFormField><UFormField label="Email"><UInput value="user@bisnisku.id" disabled class="w-full" /></UFormField><UFormField label="Nomor telepon"><UInput placeholder="Masukkan nomor telepon" class="w-full" /></UFormField><UButton label="Simpan" type="submit" /></form></section>
    </UContainer>
    <MarketplaceFooter />
  </main>
</template>
