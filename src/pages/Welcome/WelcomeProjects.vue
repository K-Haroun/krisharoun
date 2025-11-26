<script setup>
import ProjectCard from "@/components/ProjectCard.vue";
import gplogistics from "@/assets/images/gplogistics.png";
import gplcustoms from "@/assets/images/gplcustoms.png";
import dnd from "@/assets/images/dnd.png";
import Heading from "@/components/Heading.vue";
</script>

<template>
  <div>
    <Heading>
      Projects
    </Heading>

    <div class="mx-auto pt-10 pb-10 md:pb-20">
      <div class="flex justify-center flex-wrap mx-auto gap-5">
        <ProjectCard link="https://www.gp-logistics.co.uk/" title="GP Logistics" :img="gplogistics"
          v-motion-slide-visible-once-bottom>
          Assigned by company director to work on company website. Drastically improved
          website SEO, speed and functionality, modernised and redesigned navigation UI,
          added multiple new pages and components.
        </ProjectCard>
        <ProjectCard link="https://www.gpl-customs.co.uk/" title="GPL Customs" :img="gplcustoms"
          v-motion-slide-visible-once-bottom>
          Same company, their second website.
        </ProjectCard>
        <ProjectCard link="https://fpllegends.on-forge.com/" title="FPL Legends" :img="fpllegends"
          v-motion-slide-visible-once-bottom>
          Fantasy Premier League web app solo built using Laravel / Inertia / Vue & official FPL API.
        </ProjectCard>
      </div>
    </div>
  </div>
</template>
