<template>
  <nav class="bg-coolGray-800">
    <div class="container flex items-center justify-between mx-auto">
      <div class="flex items-center space-x-4">
        <noto:videocassette class="w-16 h-16" />
        <p
          class="text-4xl tracking-wider text-transparent bg-gradient-to-r from-blue-500 to-green-500 font-extralight bg-clip-text"
        >
          Movies<span class="font-bold">DB</span>
        </p>
      </div>
      <div>
        <div v-if="isAuthenticated" class="flex items-center space-x-4">
          <p class="text-coolGray-200">Welcome {{ user?.displayName }}</p>
          <button
            @click="out"
            class="px-8 py-2 font-semibold bg-orange-500 rounded-full focus:ring-red-900 focus:ring-4 focus:outline-none text-coolGray-100 hover:bg-orange-700"
          >
            Logout
          </button>
        </div>
        <div v-else>
          <button
            @click="signIn"
            class="px-8 py-2 font-semibold bg-green-500 rounded-full focus:ring-green-900 focus:ring-4 focus:outline-none text-coolGray-100 hover:bg-green-700"
          >
            Login
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
  import { authentication } from '~/helpers/useFirebase'
  import { movies, page } from '~/helpers/useMovies'

  const { signIn, signOut, isAuthenticated, user } = authentication()

  const out = () => {
    signOut()
    page.value = 1
    movies.value = []
  }
</script>
