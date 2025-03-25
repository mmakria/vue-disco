<script setup>

import CardAlbum from "@/components/CardAlbum.vue";
import {records} from '/src/assets/js/allRecords'
import {ref} from "vue";

const albums = ref(records)
// function for adding or decrement stocks

</script>

<template>
  <main class="bg-white py-5 ml-6 basis-auto">
    <card-album
        v-for="album in albums"
        :key="album.id"
        :album="album"
        :id="album.id"
    />
  </main>
</template>
<style scoped>
</style>