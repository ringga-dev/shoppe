<script setup lang="ts">
const email = ref('')
const password = ref('')
</script>

<template>
  <main class="min-h-screen bg-[#f5f5f5]">
    <AuthHeader prompt="Belum punya akun?" link="/auth/register" link-label="Daftar" />
    <section class="flex min-h-[calc(100vh-144px)] items-center justify-center px-4 py-10">
      <div class="grid w-full max-w-5xl overflow-hidden bg-white shadow-sm md:grid-cols-[1fr_420px]">
        <div class="hidden items-center justify-center bg-gradient-to-br from-[#ee4d2d] to-[#ff7337] p-12 text-center text-white md:flex">
          <div>
            <div class="mx-auto flex size-28 items-center justify-center rounded-3xl border-4 border-white text-7xl font-light">B</div>
            <h1 class="mt-7 text-3xl font-medium">Belanja mudah bersama BisnisKu</h1>
            <p class="mt-3 text-sm text-orange-50">Satu akun untuk belanja, berjualan, dan mengelola toko Anda.</p>
          </div>
        </div>
        <div class="p-7 sm:p-10">
          <h2 class="text-xl font-medium text-gray-800">Log In</h2>
          <form class="mt-7 space-y-4" @submit.prevent>
            <UInput v-model="email" type="email" placeholder="Email atau nomor telepon" size="lg" class="w-full" />
            <UInput v-model="password" type="password" placeholder="Password" size="lg" class="w-full" />
            <UButton label="LOG IN" type="submit" block size="lg" class="rounded-sm bg-[#ee4d2d] text-white hover:bg-[#d94427]" />
          </form>
          <div class="my-5 flex items-center gap-3 text-xs text-gray-400"><span class="h-px flex-1 bg-gray-200" />ATAU<span class="h-px flex-1 bg-gray-200" /></div>
          <div class="grid grid-cols-2 gap-2">
            <UButton label="Facebook" color="neutral" variant="outline" icon="i-lucide-facebook" class="rounded-sm" />
            <UButton label="Google" color="neutral" variant="outline" icon="i-lucide-chrome" class="rounded-sm" />
          </div>
          <div class="mt-5 flex justify-between text-xs">
            <NuxtLink to="/auth/forgot_password" class="text-blue-500">Lupa password?</NuxtLink>
            <NuxtLink to="/auth/register" class="text-[#ee4d2d]">Daftar akun baru</NuxtLink>
          </div>
        </div>
      </div>
    </section>
    <AuthFooter />
  </main>
</template>
