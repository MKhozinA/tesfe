<template>
  <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
    <div v-for="user in users" 
         :key="user.id" 
         class="bg-white overflow-hidden rounded-lg border border-gray-200 hover:border-gray-300 transition-all duration-200 cursor-pointer"
         @click="$emit('select-user', user)">
      <div class="p-5">
        <div class="flex items-start space-x-4">
          <div class="flex-shrink-0">
            <div class="w-10 h-10 bg-blue-50 rounded-full flex items-center justify-center">
              <span class="text-blue-600 font-semibold text-base">
                {{ user.name.charAt(0) }}
              </span>
            </div>
          </div>
          <div class="flex-1 min-w-0">
            <h2 class="text-base font-medium text-gray-900 truncate group-hover:text-blue-600">
              {{ user.name }}
            </h2>
            <p class="text-sm text-gray-500 truncate">{{ user.email }}</p>
          </div>
        </div>
        <div class="mt-4 pt-4 border-t border-gray-100">
          <div class="flex items-center text-sm text-gray-500">
            <svg class="w-3.5 h-3.5 text-gray-400" fill="none" stroke="currentColor" viewBox="0 0 24 24" 
                 stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" 
                    d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/>
              <path stroke-linecap="round" stroke-linejoin="round" 
                    d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/>
            </svg>
            <span class="ml-1.5 truncate">{{ user.address.street }}, {{ user.address.city }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    users: {
      type: Array,
      required: true
    }
  }
}
</script> 