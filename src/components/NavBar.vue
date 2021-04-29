<template>
  <nav class="bg-coolGray-700">
    <div class="container flex items-center justify-between mx-auto">
      <div class="flex items-center space-x-4">
        <noto:videocassette class="w-16 h-16" />
        <p
          class="text-4xl tracking-wider text-transparent bg-gradient-to-r from-purple-500 via-pink-400 to-red-500 font-extralight bg-clip-text"
        >
          Movies<span class="font-bold">DB</span>
        </p>
      </div>
      <div>
        <div v-if="isAuthenticated" class="flex items-center space-x-4">
          <p class="text-coolGray-200">Welcome {{ user }}</p>
          <button
            @click="signOut"
            class="px-8 py-2 font-semibold bg-red-600 rounded-full focus:ring-red-900 focus:ring-4 focus:outline-none text-coolGray-100 hover:bg-red-800"
          >
            Logout
          </button>
        </div>
        <div v-else>
          <button
            @click="signIn"
            class="px-8 py-2 font-semibold bg-green-600 rounded-full focus:ring-green-900 focus:ring-4 focus:outline-none text-coolGray-100 hover:bg-green-800"
          >
            Login
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'

const isAuthenticated = ref(false)
const user = ref('')

const signIn = () => {
  isAuthenticated.value = true
  user.value = 'Mario'
}

const signOut = () => {
  isAuthenticated.value = false
  user.value = ''
}
</script>
