<script setup>
import { ref } from "vue";

// Define reactive variables
const postCreating = ref(false);
const fileInput = ref(null);

// Define method to handle file input click
const handleClick = () => {
  fileInput.value.click();
};
</script>

<template>
  <div class="px-3 bg-gray-800 py-2 rounded-2xl mb-2">
    <h2
      class="font-semibold text-center text-xl text-gray-800 dark:text-blue-400 leading-tight px-5"
    >
      Timeline
    </h2>
    <div class="py-8">
      <div
        @click="postCreating = true"
        class="py-2 px-2 text-gray-100 border-2 border-blue-400 rounded-lg cursor-pointer"
      >
        Click Here to Create New Post
      </div>
      <div v-if="postCreating">
        <div class="flex gap-2 justify-between mt-2">
          <button
            type="button"
            class="btn btn-secondary rounded-xl hover:bg-gray-200"
            @click="handleClick"
          >
            Attach File
          </button>

          <!-- Hidden File Input -->
          <input type="file" id="dropzone-file" class="hidden" ref="fileInput" />

          <button type="button" class="btn btn-primary rounded-xl hover:btn-info w-24">
            Post
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.cursor-pointer {
  cursor: pointer;
}
</style>
