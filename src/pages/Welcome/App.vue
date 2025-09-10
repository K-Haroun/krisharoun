<script setup>
import ContactMe from "@/components/ContactMe.vue";
import WelcomeMid from "./WelcomeMid.vue";
import WelcomeProjects from "./WelcomeProjects.vue";
import WelcomeSkills from "./WelcomeSkills.vue";
import WelcomeTop from "./WelcomeTop.vue";
</script>

<template>
  <div class="main">
    <WelcomeTop />
    <div class="bg-tertiary flex flex-col justify-center items-center drop-shadow-2xl">
      <div class="w-80 md:w-180 py-10 md:py-20">
        <WelcomeMid />
        <WelcomeSkills />
        <WelcomeProjects />
        <ContactMe />
      </div>
    </div>
  </div>
</template>
