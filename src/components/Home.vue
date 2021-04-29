<template>
    <div class="container grid gap-4 mx-auto my-4 text-center lg:grid-cols-2">
      <Card v-for="(n, index) in 10" :key="index" />
    </div>
    <div class="flex items-center justify-center mb-4 space-x-2">
      <div>
        <button class="px-4 py-2 bg-white rounded">-</button>
      </div>
      <div>
        <p class="px-4 text-coolGray-200">Page 1 of 3</p>
      </div>
      <div>
        <button class="px-4 py-2 bg-white rounded">+</button>
      </div>
    </div>
</template>
