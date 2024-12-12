<template>
  <div class="max-w-2xl">
    <div class="relative">
      <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
        <svg class="w-4 h-4 text-gray-400" fill="none" stroke="currentColor" viewBox="0 0 24 24" 
             stroke-width="2">
          <path stroke-linecap="round" stroke-linejoin="round" 
                d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"/>
        </svg>
      </div>
      <input
        type="text"
        v-model="searchText"
        @input="$emit('search', searchText)"
        placeholder="Cari pengguna berdasarkan nama..."
        class="block w-full pl-9 pr-4 py-2.5 border border-gray-200 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent bg-white text-gray-900 placeholder-gray-500 text-sm"
      >
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const searchText = ref('')
    return { searchText }
  }
}
</script> 