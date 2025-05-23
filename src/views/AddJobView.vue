<script setup>
import router from '@/router';
import { reactive } from 'vue';
import { useToast } from 'vue-toastification';
import axios from 'axios';

const form = reactive({
  name: 'Empress....',
  social: '',
  description: '',
  type: '',
  location: '',
  company: {
    name: '',
    description: '',
    contactEmail: '',
    contactPhone: '',
  },
});

const toast = useToast();

const handleSubmit = async () => {
  const newJob = {
    title: form.title,
    type: form.type,
    location: form.location,
    description: form.description,
    company: {
      contactEmail: form.company.contactEmail,
    },
  };

  try {
    const response = await axios.post('/api/jobs', newJob);
    toast.success('Registration Successful');
    router.push(`/jobs/${response.data.id}`);
  } catch (error) {
    console.error('Error fetching job', error);
    toast.error("Sorry, this does't work yet");
  }
};
</script>

<template>
  <section class="bg-gray-950">
    <div class="container m-auto max-w-2xl py-24">
      <div
          class="bg-white bg-opacity-95 px-6 py-8 mb-4 shadow-md rounded-md border m-4 md:m-0"
      >
        <form @submit.prevent="handleSubmit">
          <h2 class="text-3xl text-center font-semibold mb-6">Join waitlist</h2>

          <div class="mb-4">
            <label for="type" class="block text-gray-700 font-bold mb-2"
            >type</label
            >
            <select
                v-model="form.type"
                id="type"
                name="type"
                class="border rounded w-full py-2 px-3"
                required
            >
              <option value="Dom">Domme</option>
              <option value="sub">sub</option>
            </select>
          </div>

          <div class="mb-4">
            <label class="block text-gray-700 font-bold mb-2"
            >Name</label
            >
            <input
                type="text"
                v-model="form.title"
                id="name"
                name="name"
                class="border rounded w-full py-2 px-3 mb-2"
                placeholder="Empress..."
                required
            />
          </div>
          <div class="mb-4">
            <label for="description" class="block text-gray-700 font-bold mb-2"
            >Description</label
            >
            <textarea
                id="description"
                v-model="form.description"
                name="description"
                class="border rounded w-full py-2 px-3"
                rows="4"
                placeholder="Superior Woman seeking hard working servants..."
            ></textarea>
          </div>

          <div class="mb-4">
            <label for="company" class="block text-gray-700 font-bold mb-2"
            >City</label
            >
            <input
                type="text"
                v-model="form.company.name"
                id="company"
                name="company"
                class="border rounded w-full py-2 px-3"
                placeholder="Berlin"
            />
          </div>

          <div class="mb-4">
            <label
                for="contact_email"
                class="block text-gray-700 font-bold mb-2"
            >Contact Email</label
            >
            <input
                type="email"
                v-model="form.company.contactEmail"
                id="contact_email"
                name="contact_email"
                class="border rounded w-full py-2 px-3"
                placeholder="me@you.net"
                required
            />
          </div>
             <div>
            <button
                class="bg-yellow-900 hover:bg-yellow-950 text-white font-bold py-2 px-4 rounded-full w-full focus:outline-none focus:shadow-outline"
                type="submit"
            >
              Register
            </button>
          </div>
        </form>
      </div>
    </div>
  </section>
</template>