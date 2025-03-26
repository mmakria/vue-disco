<script setup>
import NavBar from "./components/NavBar.vue"
import FilterAside from "@/components/FilterAside.vue";
import DisplayCardAlbum from "@/components/DisplayCardAlbum.vue";
import {ref} from "vue";

const sortValue = ref("")
const sortBy = (dataSelect) => {
  console.log(dataSelect)
  sortValue.value = dataSelect
}

const isStock = ref(null)
const isInStock = (dataStock) => {
  console.log(dataStock)
  isStock.value = dataStock
}
</script>

<template>
  <NavBar/>
  <div class="min-h-screen flex flex-col">
    <div class="flex flex-row ">
      <FilterAside
          @isInStock="isInStock"
          @sortBy="sortBy"
      />
      <DisplayCardAlbum
          :isStock="isStock"
          :isSelected="sortValue"
      />
    </div>
  </div>
</template>

<style scoped>
</style>
