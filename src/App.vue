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
            <input type="text" class="form-control w-50">
          </div>
          <div class="d-flex justify-content-center ">
            <p class="align-middle">Name:</p>
            <select class="form-select w-50">
              <option selected>Select enum</option>
              <option >fasz</option>
            </select>
          </div>
          <div class="d-flex justifi-content-start">
            <p class="">For Sale:</p>
            <input type="checkbox">
          </div>
          <div class="d-flex justify-content-center">
            <p class="align-middle">Price:</p>
            <input type="text" class="form-control w-50">
          </div>
        </div>
        <div class="card-footer">
          <button class="btn btn-success">Create</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>




</script>

<style scoped></style>
