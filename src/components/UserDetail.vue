<template>
  <div class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50">
    <div class="bg-white rounded-xl max-w-2xl w-full mx-4 shadow-2xl">
      <div class="p-6 border-b">
        <div class="flex justify-between items-center">
          <div class="flex items-center">
            <div class="w-12 h-12 bg-blue-100 rounded-full flex items-center justify-center">
              <span class="text-blue-600 font-bold text-xl">{{ user.name.charAt(0) }}</span>
            </div>
            <h2 class="text-2xl font-bold text-gray-800 ml-4">{{ user.name }}</h2>
          </div>
          <button @click="$emit('close')" 
                  class="p-2 hover:bg-gray-100 rounded-full transition-colors">
            <svg class="w-6 h-6 text-gray-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
            </svg>
          </button>
        </div>
      </div>
      
      <div class="p-6 space-y-6">
        <div class="grid gap-6 md:grid-cols-2">
          <div class="bg-gray-50 p-4 rounded-lg">
            <h3 class="font-bold text-lg text-gray-800 mb-3">Informasi Pribadi</h3>
            <div class="space-y-2">
              <p class="flex items-center text-gray-600">
                <span class="font-medium w-24">Username:</span> {{ user.username }}
              </p>
              <p class="flex items-center text-gray-600">
                <span class="font-medium w-24">Email:</span> {{ user.email }}
              </p>
              <p class="flex items-center text-gray-600">
                <span class="font-medium w-24">Phone:</span> {{ user.phone }}
              </p>
              <p class="flex items-center text-gray-600">
                <span class="font-medium w-24">Website:</span> 
                <a :href="'https://' + user.website" 
                   class="text-blue-600 hover:underline"
                   target="_blank">
                  {{ user.website }}
                </a>
              </p>
            </div>
          </div>

          <div class="bg-gray-50 p-4 rounded-lg">
            <h3 class="font-bold text-lg text-gray-800 mb-3">Alamat</h3>
            <div class="space-y-2">
              <p class="flex items-center text-gray-600">
                <span class="font-medium w-24">Jalan:</span> {{ user.address.street }}
              </p>
              <p class="flex items-center text-gray-600">
                <span class="font-medium w-24">Suite:</span> {{ user.address.suite }}
              </p>
              <p class="flex items-center text-gray-600">
                <span class="font-medium w-24">Kota:</span> {{ user.address.city }}
              </p>
              <p class="flex items-center text-gray-600">
                <span class="font-medium w-24">Kode Pos:</span> {{ user.address.zipcode }}
              </p>
            </div>
          </div>

          <div class="bg-gray-50 p-4 rounded-lg md:col-span-2">
            <h3 class="font-bold text-lg text-gray-800 mb-3">Perusahaan</h3>
            <div class="space-y-2">
              <p class="flex items-center text-gray-600">
                <span class="font-medium w-24">Nama:</span> {{ user.company.name }}
              </p>
              <p class="flex items-center text-gray-600">
                <span class="font-medium w-24">Catch Phrase:</span> {{ user.company.catchPhrase }}
              </p>
              <p class="flex items-center text-gray-600">
                <span class="font-medium w-24">BS:</span> {{ user.company.bs }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    user: {
      type: Object,
      required: true
    }
  }
}
</script> 