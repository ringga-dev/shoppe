<script setup lang="ts">
const email = ref('')
</script>

<template>
  <main class="min-h-screen bg-[#f5f5f5]">
    <AuthHeader prompt="Ingat password?" link="/auth/login" link-label="Log In" />
    <section class="flex min-h-[calc(100vh-144px)] items-center justify-center px-4 py-10">
      <div class="w-full max-w-md bg-white p-7 shadow-sm sm:p-10">
        <NuxtLink to="/auth/login" class="text-sm text-gray-500">‹ Kembali ke login</NuxtLink>
        <h1 class="mt-6 text-xl font-medium text-gray-800">Reset password</h1>
        <p class="mt-2 text-sm text-gray-500">Masukkan email untuk menerima tautan reset password.</p>
        <form class="mt-7 space-y-4" @submit.prevent>
          <UInput v-model="email" type="email" placeholder="Email atau nomor telepon" size="lg" class="w-full" />
          <UButton label="KIRIM" type="submit" block size="lg" class="rounded-sm bg-[#ee4d2d] text-white hover:bg-[#d94427]" />
        </form>
      </div>
    </section>
    <AuthFooter />
  </main>
</template>
