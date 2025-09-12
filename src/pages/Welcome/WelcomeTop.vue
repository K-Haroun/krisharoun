<script setup>
import { onMounted, ref } from "vue";

const show1 = ref(false);
const show2 = ref(false);

onMounted(() => {
  show1.value = true;

  setTimeout(() => {
    show2.value = true;
  }, 700);
});
</script>

<template>
  <div class="flex justify-center items-center gap-10 md:gap-10">
    <div class="w-30 md:w-100">
      <Transition name="slide2">
        <div v-if="show2" class="flex flex-col justify-start gap-5">
          <h2 class="text-xl md:text-4xl text-secondary font-bold text-shadow-md">
            Hey, I'm Kris
          </h2>
          <p class="text-xs md:text-lg">
            I am a passionate web & software developer. My goal is to make a change in the
            world through the great power of coding!
          </p>
        </div>
      </Transition>
    </div>

    <Transition name="slide1">
      <img
        v-if="show1"
        src="@/assets/images/me.png"
        alt="me.png"
        class="h-50 md:h-100 w-auto"
      />
    </Transition>
  </div>
</template>

<style>
.slide1-enter-active {
  transition: all 0.5s ease-out;
}

.slide1-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide1-enter-from,
.slide1-leave-to {
  transform: translateX(-200px);
  opacity: 0;
}

.slide2-enter-active {
  transition: all 0.5s ease-out;
}

.slide2-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide2-enter-from,
.slide2-leave-to {
  transform: translateX(-200px);
  opacity: 0;
}
</style>
