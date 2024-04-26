<template>
  <div class="flex justify-center min-h-screen h-full font-semibold">
    <div class="mx-auto my-auto sm:w-1/2 lg:w-1/3">
      <div class="bg-gradient-to-r from-lime-500 to-green-900 text-center rounded-lg border-2 border-gray-800">
        <div class="border-green-950 border-b-2 p-1">
          <div class="flex justify-between">
            <p>House Menu</p>
            <button class="bg-transparent hover:bg-red-700 text-black hover:text-white font-bold p-1 px-2 rounded-lg"
              @click="exit">
              X
            </button>
          </div>
        </div>
        <div class="w-1/2 mx-auto">
          <div class="flex mb-3 mt-3">
            <p class="me-2">Name:</p>
            <input type="text"
              class="border border-gray-300 text-gray-900 text-sm rounded focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
              v-model="name">
          </div>
          <div class="flex mb-3 mt-3">
            <p class="me-2">Property List:</p>
            <select
              class="text-center border border-gray-300 text-gray-900 text-sm rounded focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500 w-1/2"
              v-model="type">
              <option v-for="item in enums" :value="item">{{ item }}</option>
            </select>
          </div>
          <div class="flex mb-3 mt-3 ">
            <p class="me-2">For Sale:</p>
            <input type="checkbox" v-model="forsale">
          </div>
          <div class="flex mb-3 mt-3 ">
            <p class="me-2">Price:</p>
            <input type="text"
              class="border border-gray-300 text-gray-900 text-sm rounded focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
              v-model="price">
          </div>
        </div>
        <div class="">
          <button class="m-3 text-white p-1 px-2 rounded font-bold bg-lime-950" @click="create">Create</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>

import axios from 'axios';
import { ref } from 'vue';


const enums = ['HOUSE', 'GARAGE', 'APARTMAN', 'STORAGE', 'WEEDFARM', 'METHFARM']
const name = ref("unnamed")
const type = ref("House")
const forsale = ref(true)
const price = ref(50000)

function exit() {
  axios.post(`https://${GetParentResourceName()}/mate-house:exit`, {})
}


function create() {
  console.log(JSON.stringify({
    data: {
      type: type.value,
      price: price.value,
      name: name.value,
      forSale: price.value
    }
  }))
  axios.post(`https://${GetParentResourceName()}/mate-house:CreateProperty`, JSON.stringify({
    data: {
      type: type.value,
      price: price.value,
      name: name.value,
      forSale: price.value
    }
  }))
}

</script>