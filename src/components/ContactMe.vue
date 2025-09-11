<script setup>
import { Send } from "lucide-vue-next";
import Heading from "./Heading.vue";
import { ref } from "vue";

const email = ref("");
const message = ref("");
const success = ref(false);

const handleSubmit = async () => {
  const formData = new FormData();
  formData.append("form-name", "contact");
  formData.append("email", email.value);
  formData.append("message", message.value);

  try {
    await fetch("/", {
      method: "POST",
      body: formData,
    });
    // success
    email.value = "";
    message.value = "";
    success.value = true;
    // hide toast after 3s
    setTimeout(() => (success.value = false), 3000);
  } catch (err) {
    console.error(err);
  }
};
</script>

<template>
  <!-- Toast -->
  <Teleport to="body">
  <div
    v-if="success"
    class="fixed top-4 left-1/2 -translate-x-1/2 bg-green-500 text-white px-4 py-2 rounded shadow z-50"
  >
    Thank you for your message!
  </div>
</Teleport>

  <Heading> Get in touch! </Heading>
  <p class="text-black/70 mt-5 text-center text-xs md:text-sm">
    You can contact me directly at kris.haroun@gmail.com, call me on +44 7497833969 or
    fill in the form below 👇
  </p>

  <form name="contact" method="post" data-netlify="true" data-netlify-honeypot="bot-field" @submit.prevent="handleSubmit">
    <input type="hidden" name="form-name" value="contact" />
    <div
      class="mt-7 p-10 border border-secondary/5 rounded bg-secondary/5 flex flex-col justify-center items-center gap-3">
      <input type="email" name="email" v-model="email" placeholder="Your email"
        class="p-4 bg-tertiary/50 border border-secondary rounded-md w-full md:w-2/3 h-10" required />
      <textarea type="text" name="message" v-model="message" placeholder="Your message"
        class="w-full md:w-2/3 h-50 p-4 border border-secondary rounded-md resize-none bg-tertiary/50" required />
      <button type="submit"
        class="mr-37 md:mr-74 flex gap-3 items-center justify-center py-2 px-3 md:py-2 md:px-4 border border-secondary rounded-md bg-secondary/50 hover:bg-secondary/70 cursor-pointer text-xs md:text-lg">
        Submit
        <Send class="size-3 md:size-5" />
      </button>
    </div>
  </form>
</template>
