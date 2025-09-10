<script setup>
import { ref } from "vue";

const tabs = ["Front", "Back", "Database", "Other"];
const front = ["HTML", "CSS", "JavaScript", "Vue", "TailwindCSS", "Bootstrap 5"];
const back = ["PHP", "Java", "Laravel", "Spring boot", "Node"];
const db = ["MySQL", "PostgreSQL", "SQLite"];
const other = ["AWS", "Azure", "Git", "Github", "Bitbucket"];
const currentTab = ref(front);

const tabData = {
  Front: front,
  Back: back,
  Database: db,
  Other: other,
};

const changeTab = (tab) => {
  currentTab.value = tabData[tab];
};
</script>

<template>
  <div class="w-full h-90">
    <div class="w-fit flex gap-3 mx-auto mt-10">
      <h2
        v-for="tab in tabs"
        @click="changeTab(tab)"
        class="flex justify-center items-center w-fit py-2 px-3 text-tertiary bg-secondary/70 border rounded-md hover:bg-secondary/80 transition-colors duration-300 cursor-pointer text-sm md:tex-md"
      >
        {{ tab }}
      </h2>
    </div>
    <div class="flex justify-start flex-wrap gap-5 my-20 w-70 md:w-150 mx-auto">
      <TransitionGroup
        name="pop"
        tag="div"
        class="flex justify-start flex-wrap gap-5 w-full mx-auto"
      >
        <div
          v-for="(item, index) in currentTab"
          :key="item"
          class="md:basis-1/4 flex items-center justify-center gap-3 border border-primary rounded-full bg-primary/70 w-fit p-2 mx-auto drop-shadow-md"
          :style="{
            transitionDelay: index * 100 + 'ms',
          }"
          >
          <img
            :src="`/images/skills/${item.toLowerCase()}.svg`"
            :alt="item"
            class="size-5 md:size-8"
          />
          <h2 class="font-bold text-xs md:text-md">{{ item }}</h2>
        </div>
      </TransitionGroup>
    </div>
  </div>
</template>

<style scoped>

.pop-enter-active { transition: all 0.5s ease-out; }
.pop-enter-from  { opacity: 0; transform: translateY(20px) scale(0.95); }
.pop-enter-to    { opacity: 1; transform: translateY(0)   scale(1); }

.pop-leave-active { transition: none !important; }
.pop-leave-from,
.pop-leave-to { opacity: 1; transform: none; }

</style>