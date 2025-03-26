<script setup>
import NavBar from "./components/NavBar.vue"
import FilterAside from "@/components/FilterAside.vue";
import DisplayCardAlbum from "@/components/DisplayCardAlbum.vue";
import {ref} from "vue";


const isStock = ref(null)
const isInStock = (data) => {
  console.log(data.value)
  isStock.value = data.value
}


</script>


<template>
  <NavBar/>
  <div class="min-h-screen flex flex-col">
    <div class="flex flex-row ">
      <FilterAside
          @isInStock="isInStock"
      />
      <DisplayCardAlbum
      :isStock="isStock"
      />
    </div>
  </div>
</template>

<style scoped>
</style>
