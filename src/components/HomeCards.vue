<script setup lang="ts">
import { RouterLink } from "vue-router";
import bg from '@/assets/img/Gog-D_NXsAAO8i8.jpeg';
import Card from '@/components/Card.vue'
</script>

<template>
    <section :style="{ backgroundImage: `url(${bg})` }" class="py-40 bg-cover bg-center">
      <div class="container-xl lg:container m-auto">

  <div class="grid grid-cols-1 md:grid-cols-2 gap-4 p-4 rounded-lg">
        <Card bg="bg-gray-100 bg-opacity-50">
          <h2 class="text-2xl font-bold">For subs</h2>
          <h3 class="mt-2 mb-4">
            Find an Owner that gets every part of you and worth devoting your life to.
          </h3>
          <RouterLink
              to="/jobs"
              class="inline-block bg-black text-white rounded-lg px-4 py-2 hover:bg-gray-700"
          >
            Search Dommes
          </RouterLink>
        </Card>
        <Card bg="bg-yellow-700 bg-opacity-25" >
          <h2 class="text-2xl font-bold">For Dommes</h2>
          <h3 class="mt-2 mb-4">
            Earn passive income and embrace Your natural Power.
          </h3>
          <RouterLink
              to="/jobs/add"
              class="inline-block bg-yellow-900 text-white rounded-lg px-4 py-2 hover:bg-yellow-950"
          >
            Join Waitlist
          </RouterLink>
        </Card>
      </div>
    </div>
  </section>
</template>
