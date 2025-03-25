<script setup>
import NavBar from "./components/NavBar.vue"
import FilterAside from "@/components/FilterAside.vue";
import DisplayCardAlbum from "@/components/DisplayCardAlbum.vue";
</script>


<template>
  <NavBar/>
  <div class="min-h-screen flex flex-col">
    <div class="flex flex-row ">
      <FilterAside/>
      <DisplayCardAlbum/>
    </div>
  </div>
</template>

<style scoped>
</style>
