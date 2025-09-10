<script setup>
import NavItem from "@/components/ui/nav/NavItem.vue";
import { Head, Link, router } from "@inertiajs/vue3";
</script>

<template>
  <div
    class="flex flex-col items-center text-[#1b1b18] lg:justify-center"
  >
    <header class="w-full text-sm">
    <div class="h-50 bg-gradient-to-r from-primary to-[#a87648]">
    <div class="h-full ml-5 flex flex-col text-start justify-center">
        <h1 class="text-[58px] font-extrabold text-primary-foreground text-shadow-lg">
            KRIS HAROUN
        </h1>
        <p class="italic">Portfolio Website</p>
    </div>
    </div>
      <nav class="flex items-center justify-end bg-secondary/70 text-secondary-foreground">
      <div class="flex mr-10">      
        <NavItem href="/">
            Home
        </NavItem>
        <NavItem href="/">
            Projects
        </NavItem>
        <NavItem href="/">
            Contact
        </NavItem>
      </div>
      </nav>
    </header>
  </div>
</template>
