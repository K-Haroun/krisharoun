<script setup>
import ItemCard from "@/components/ItemCard.vue";

import lebanon from "@/assets/images/lebanon.png";
import lithuania from "@/assets/images/lithuania.png";
import wales from "@/assets/images/wales.png";
import Heading from "@/components/Heading.vue";

const items = [
  { img: lebanon, text: "Half Lebanese" },
  { img: lithuania, text: "Half Lithuanian" },
  { img: wales, text: "Living in Wales" },
];
</script>

<template>
  <Heading>
    A bit about me
  </Heading>

  <div class="flex justify-center items-start py-5 gap-4">
    <ItemCard
      v-for="(item, index) in items"
      :key="index"
      :item="item"
      v-motion-pop-visible-once
      :duration="index * 300"
    />
  </div>

  <div class="mt-10">
    <p>
      My name is Kristofas, I'm a VILT stack developer with some Java and Spring Boot
      experience. I have been coding for 3 years and have 1 year commercial experience in
      web development.
      <br />
      <br />
      I completed a Bsc in Computer Science at Swansea University, after some time of
      confusion in my early 20s I truly found my passion in coding, I finished multiple
      online courses and worked on various projects. In 2024 I joined GPL Customs and was
      assigned by the director of the company to work on their websites. The company were
      really happy with the results and since then I have been working a dual role, web
      development and customs clearance.
      <br />
      <br />
      I would love to join a team of software engineers where I can put my passion and
      skills to good use while growing as a person.
    </p>
  </div>
</template>
