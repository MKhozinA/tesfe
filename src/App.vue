<template>
  <div class="min-h-screen bg-gray-100">
    <nav class="bg-white shadow-sm border-b">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between h-16 items-center">
          <h1 class="text-xl font-semibold text-gray-800">Daftar Pengguna</h1>
        </div>
      </div>
    </nav>

    <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
      <div class="mb-8">
        <UserSearch @search="handleSearch" />
      </div>
      
      <div v-if="selectedUser">
        <UserDetail 
          :user="selectedUser" 
          @close="selectedUser = null" 
        />
      </div>
      
      <UserList 
        v-else
        :users="filteredUsers" 
        @select-user="handleSelectUser" 
      />
    </main>
  </div>
</template>

<script>
import { ref, computed } from 'vue'
import UserList from './components/UserList.vue'
import UserDetail from './components/UserDetail.vue'
import UserSearch from './components/UserSearch.vue'

export default {
  components: {
    UserList,
    UserDetail,
    UserSearch
  },
  setup() {
    const users = ref([])
    const selectedUser = ref(null)
    const searchQuery = ref('')

    const filteredUsers = computed(() => {
      return users.value.filter(user => 
        user.name.toLowerCase().includes(searchQuery.value.toLowerCase())
      )
    })

    const fetchUsers = async () => {
      try {
        const response = await fetch('https://jsonplaceholder.typicode.com/users')
        users.value = await response.json()
      } catch (error) {
        console.error('Error fetching users:', error)
      }
    }

    const handleSelectUser = (user) => {
      selectedUser.value = user
    }

    const handleSearch = (query) => {
      searchQuery.value = query
    }

    // Fetch users when component mounts
    fetchUsers()

    return {
      users,
      selectedUser,
      filteredUsers,
      handleSelectUser,
      handleSearch
    }
  }
}
</script>
