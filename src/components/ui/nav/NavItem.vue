<script setup>
import { Link } from '@inertiajs/vue3';

    const props = defineProps(['href'])
</script>
<template>
  <Link
    :href="props.href"
    class="text-sm text-secondary-foreground cursor-pointer hover:bg-secondary py-3 px-4 transition-colors duration-300"
  >
    <slot />
  </Link>
</template>
