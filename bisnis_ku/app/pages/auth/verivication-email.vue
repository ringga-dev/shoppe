<template>
  <main class="flex min-h-screen items-center justify-center bg-elevated px-4 py-10">
    <UCard class="w-full max-w-md text-center">
      <div class="mx-auto flex size-12 items-center justify-center rounded-full bg-primary/10 text-primary">✉</div>
      <h1 class="mt-5 text-2xl font-bold text-highlighted">Verifikasi email Anda</h1>
      <p class="mt-3 text-muted">Tautan verifikasi telah dikirim ke email Anda. Periksa kotak masuk untuk mengaktifkan akun.</p>
      <UButton label="Kembali ke login" to="/auth/login" class="mt-6" />
    </UCard>
  </main>
</template>
