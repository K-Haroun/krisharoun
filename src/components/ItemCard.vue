<script setup>
const props = defineProps({ item: Object });
</script>

<template>
  <div
    class="text-center my-5 md:my-10"
  >
    <img :src="item.img" alt="" class="h-20 md:h-70 w-auto mx-auto" />
    <p>{{ item.text }}</p>
  </div>
</template>
