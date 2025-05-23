<script setup>
    import { defineProps } from 'vue';

defineProps({
  title: {
    type: String,
    default: 'FemdomFunds',
  },
  subtitle: {
    type: String,
    default: 'Authorized and secure platform to connect with verified professional femdoms – ensuring trust, privacy, and safety with every interaction',
  }
});
</script>

<template>
  <section class="bg-black py-10">
    <div
        class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col items-center"
    >
      <div class="text-center">
        <h1
            class="text-4xl font-extrabold text-white sm:text-5xl md:text-6xl"
        >
          {{ title }}
        </h1>
        <p class="my-4 text-xl text-white">
         {{ subtitle }}
        </p>
      </div>
    </div>
  </section>
</template>

<style scoped>

</style>