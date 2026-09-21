<template>
  <main class="flex min-h-screen items-center justify-center bg-elevated px-4 py-10">
    <UCard class="w-full max-w-md text-center">
      <h1 class="text-2xl font-bold text-highlighted">Selamat datang di BisnisKu</h1>
      <p class="mt-2 text-muted">Masuk atau buat akun untuk melanjutkan.</p>
      <div class="mt-6 grid gap-3">
        <UButton label="Masuk" to="/auth/login" block />
        <UButton label="Buat akun baru" color="neutral" variant="outline" to="/auth/register" block />
      </div>
    </UCard>
  </main>
</template>
