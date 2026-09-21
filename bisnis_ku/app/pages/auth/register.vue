<script setup lang="ts">
const phone = ref('')
const password = ref('')
const confirmation = ref('')
</script>

<template>
  <main class="min-h-screen bg-[#f5f5f5]">
    <AuthHeader prompt="Sudah punya akun?" link="/auth/login" link-label="Log In" />
    <section class="flex min-h-[calc(100vh-144px)] items-center justify-center px-4 py-10">
      <div class="w-full max-w-md bg-white p-7 shadow-sm sm:p-10">
        <h1 class="text-xl font-medium text-gray-800">Daftar</h1>
        <form class="mt-7 space-y-4" @submit.prevent>
          <UInput v-model="phone" placeholder="Nomor telepon atau email" size="lg" class="w-full" />
          <UInput v-model="password" type="password" placeholder="Password" size="lg" class="w-full" />
          <UInput v-model="confirmation" type="password" placeholder="Konfirmasi password" size="lg" class="w-full" />
          <UButton label="DAFTAR" type="submit" block size="lg" class="rounded-sm bg-[#ee4d2d] text-white hover:bg-[#d94427]" />
        </form>
        <p class="mt-6 text-center text-xs leading-5 text-gray-500">
          Dengan mendaftar, kamu menyetujui
          <NuxtLink to="/" class="text-[#ee4d2d]">Ketentuan Layanan</NuxtLink>
          dan
          <NuxtLink to="/" class="text-[#ee4d2d]">Kebijakan Privasi</NuxtLink>
          BisnisKu.
        </p>
        <div class="my-5 flex items-center gap-3 text-xs text-gray-400"><span class="h-px flex-1 bg-gray-200" />ATAU<span class="h-px flex-1 bg-gray-200" /></div>
        <div class="grid grid-cols-2 gap-2">
          <UButton label="Facebook" color="neutral" variant="outline" icon="i-lucide-facebook" class="rounded-sm" />
          <UButton label="Google" color="neutral" variant="outline" icon="i-lucide-chrome" class="rounded-sm" />
        </div>
      </div>
    </section>
    <AuthFooter />
  </main>
</template>
