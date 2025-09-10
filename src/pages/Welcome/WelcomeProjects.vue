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
      Some of my work
    </Heading>

    <div class="mx-auto pt-10 pb-10 md:pb-20">
      <div class="flex justify-center flex-wrap mx-auto gap-5">
          <ProjectCard
            link="https://www.gp-logistics.co.uk/"
            title="GP Logistics"
            :img="gplogistics"
            v-motion-slide-visible-once-bottom
          >
            Assigned by company director to work on company website. Drastically improved
            website SEO, speed and functionality, modernised and redesigned navigation UI,
            added multiple new pages and components.
          </ProjectCard>
          <ProjectCard
            link="https://www.gpl-customs.co.uk/"
            title="GPL Customs"
            :img="gplcustoms"
            v-motion-slide-visible-once-bottom
          >
            Same company, their second website.
          </ProjectCard>
          <ProjectCard
            link="https://www.dnd.co.uk/"
            title="DnD"
            :img="dnd"
            v-motion-slide-visible-once-bottom
          >
            A game web app I built using Laravel and Vue. Full SPA, built for personal use
            for me and my friends for our DnD sessions.
            <p class="text-red-500 mt-3">Website currently not live.</p>
          </ProjectCard>
      </div>
    </div>
  </div>
</template>
