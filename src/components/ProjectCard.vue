<script setup>
    defineProps(['link', 'title', 'img'])
</script>

<template>
  <div class="border p-5 bg-black/20 rounded-md color text-black w-full">
  <div class="md:flex gap-5">
    <div class="py-2">
      <h2 class="text-sm md:text-xl font-bold">{{ title }}</h2>
      <a :href="link" class="text-xs md:text-sm underline"
        >{{ link }}</a
      >
      <div class="mt-5">
        <p class="text-xs md:text-sm">
            <slot />
        </p>
      </div>
    </div>
    <img :src="img" alt="" class="h-20 md:h-50 w-auto" />
  </div>
  </div>
</template>
