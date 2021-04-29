<template>
  <div class="flex max-w-full">
    <img src="https://via.placeholder.com/200x300.png" alt="Movie Poster" />
    <div
      class="flex flex-col justify-between p-4 leading-normal border-b border-l border-r rounded-b bg-coolGray-100 border-coolGray-400 lg:border-l-0 lg:border-t lg:border-coolGray-400 lg:rounded-b-none lg:rounded-r"
    >
      <div class="mb-8">
        <div class="mb-2 text-xl font-bold text-coolGray-900">movie.title</div>
        <p class="text-base text-coolGray-700 line-clamp-6">
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quod
          repellat non ducimus ipsa autem iste repudiandae, consequatur
          quibusdam quaerat animi a, placeat reiciendis expedita quos recusandae
          sequi! Aliquam, sequi ipsum. Lorem ipsum dolor, sit amet consectetur
          adipisicing elit. Deleniti beatae, velit similique earum voluptatibus
          ipsam fugit voluptates incidunt necessitatibus voluptatum minus ad
          quaerat, amet sunt consequuntur perspiciatis praesentium saepe
          distinctio!
        </p>
      </div>
      <div class="flex items-start justify-end">
        <div class="flex flex-col items-center">
          <button class="text-coolGray-400 hover:text-red-600">
            <mdi:heart class="w-8 h-8" />
            <span>3</span>
          </button>
        </div>
        <div class="flex flex-col items-center">
          <button @click="toggle" class="text-coolGray-400 hover:text-blue-600">
            <mdi:comment class="w-8 h-8" />
          </button>
        </div>
      </div>
    </div>
  </div>
  <Comments v-if="value" @close="toggle" />
</template>

<script setup>
import { useToggle } from '@vueuse/core'
const [value, toggle] = useToggle(false)
</script>
