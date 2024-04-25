<template>
    <div class="">

<div class="mx-auto w-50 ">
  <div class="card text-center">
    <div class="card-header">
      <div class="d-flex justify-content-between">
        <p>
          House Menu
        </p>
        <div class="btn btn-danger">
          X
        </div>
      </div>
    </div>
    <div class="card-body">
      <div class="d-flex justify-content-center">
        <p class="">Name:</p>
        <input type="text" class="form-control w-50" v-model="name">
      </div>
      <div class="d-flex justify-content-center">
        <p class="align-middle">Property List:</p>
        <select class="form-select w-50" v-model="type">
          <option selected>Select enum</option>
          <option >fasz</option>
        </select>
      </div>
      <div class="d-flex justifi-content-start">
        <p ó>For Sale:</p>
        <input type="checkbox" v-model="forsale">
      </div>
      <div class="d-flex justify-content-center">
        <p class="align-middle">Price:</p>
        <input type="text" class="form-control w-50" v-model="price">
      </div>
    </div>
    <div class="card-footer">
      <button class="btn btn-success" @click="create">Create</button>
    </div>
  </div>
</div>
</div>
</template>

<script setup>
import { ref } from 'vue';

const name = ref("unnamed")
const type = ref("House")
const forsale = ref(true)
const price = ref(50000)


function create() {
  
}

</script>