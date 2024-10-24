<template>
  <div class="min-h-screen flex items-center justify-center p-4">
    <form
      @submit.prevent="handleSubmit"
      class="bg-white border border-gray-300 rounded px-8 pt-6 pb-8 mb-4 w-full max-w-md"
    >
      <h2 class="text-2xl font-bold mb-6 text-center">Super Form (HTML)</h2>

      <!-- Text Input -->
      <div class="mb-4">
        <label class="block text-gray-700 text-sm font-bold mb-2" for="name">
          Name
        </label>
        <input
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
          id="name"
          type="text"
          placeholder="Enter your name"
          v-model="formData.name"
        />
      </div>

      <!-- Textarea -->
      <div class="mb-4">
        <label
          class="block text-gray-700 text-sm font-bold mb-2"
          for="description"
        >
          Description
        </label>
        <textarea
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
          id="description"
          placeholder="..."
          v-model="formData.description"
        ></textarea>
      </div>

      <!-- Select -->
      <div class="mb-4">
        <label
          class="block text-gray-700 text-sm font-bold mb-2"
          for="category"
        >
          Category
        </label>
        <select
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
          id="category"
          v-model="formData.category"
        >
          <option value="">Select a category</option>
          <option value="technology">Technology</option>
          <option value="science">Science</option>
          <option value="art">Art</option>
        </select>
      </div>

      <!-- Range -->
      <div class="mb-4">
        <label class="block text-gray-700 text-sm font-bold mb-2" for="rating">
          Rating: {{ formData.rating }}
        </label>
        <input
          class="w-full"
          type="range"
          id="rating"
          min="0"
          max="10"
          step="1"
          v-model="formData.rating"
        />
      </div>

      <!-- Radio Buttons -->
      <div class="mb-4">
        <span class="block text-gray-700 text-sm font-bold mb-2"
          >Radio Button</span
        >
        <div class="mt-2">
          <label class="inline-flex items-center mr-4">
            <input
              type="radio"
              class="form-radio"
              name="contactMethod"
              value="email"
              v-model="formData.contactMethod"
            />
            <span class="ml-2">Select 1</span>
          </label>
          <label class="inline-flex items-center">
            <input
              type="radio"
              class="form-radio"
              name="contactMethod"
              value="phone"
              v-model="formData.contactMethod"
            />
            <span class="ml-2">Select 2</span>
          </label>
        </div>
      </div>

      <!-- Checkbox -->
      <div class="mb-4">
        <label class="inline-flex items-center">
          <input
            type="checkbox"
            class="form-checkbox"
            v-model="formData.subscribe"
          />
          <span class="ml-2">Subscribe</span>
        </label>
      </div>

      <!-- Submit Button -->
      <div class="flex w-full items-center justify-center">
        <button
          class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
          type="submit"
        >
          Submit
        </button>
      </div>
    </form>
  </div>
</template>

<script setup>
import { ref } from "vue";

const formData = ref({
  name: "",
  description: "",
  category: "",
  rating: 5,
  contactMethod: "",
  subscribe: false,
});

const handleSubmit = () => {
  console.log("Form submitted:", formData.value);
};
</script>
