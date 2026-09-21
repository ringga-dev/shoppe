<script setup lang="ts">
defineProps<{
  product: {
    name: string
    price: string
    oldPrice?: string
    sold: string
    rating?: string
    color: string
    icon: string
  }
}>()
</script>

<template>
  <NuxtLink to="/products/1" class="group block overflow-hidden rounded-sm bg-white shadow transition hover:-translate-y-1 hover:shadow-md">
    <div :class="`relative aspect-square overflow-hidden bg-gradient-to-br ${product.color} text-white`">
      <img
        v-if="product.image"
        :src="product.image"
        :alt="product.name"
        class="size-full object-cover transition group-hover:scale-105"
      >
      <UIcon v-else :name="product.icon" class="absolute inset-0 m-auto size-20 opacity-80 transition group-hover:scale-110" />
      <UBadge label="Mall" color="primary" size="xs" class="absolute left-2 top-2" />
    </div>
    <div class="overflow-hidden p-2">
      <p class="line-clamp-2 min-h-10 text-xs text-gray-700">{{ product.name }}</p>
      <div class="mt-3 flex items-center gap-1">
        <span v-if="product.oldPrice" class="truncate text-xs text-gray-400 line-through">{{ product.oldPrice }}</span>
        <span class="truncate text-sm text-orange-500">{{ product.price }}</span>
      </div>
      <div class="mt-3 flex items-center justify-between text-xs text-gray-500">
        <span class="text-amber-400">★★★★★</span>
        <span>{{ product.sold }} terjual</span>
      </div>
    </div>
  </NuxtLink>
</template>
