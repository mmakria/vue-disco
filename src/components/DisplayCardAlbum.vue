<script setup>

import CardAlbum from "@/components/CardAlbum.vue";
import {records} from '/src/assets/js/allRecords'
import {ref} from "vue";

const allAlbums = ref(records)
const props = defineProps({
  isStock: Boolean
})
const albumsFilterd = ref(allAlbums.value.filter((album) => album.stock > 0))


</script>

<template>
  <main class="bg-white py-5 ml-6 basis-auto">
    <card-album
        v-if="!isStock"
        v-for="(album) in allAlbums"
        :key="album.id"
        :album="album"
        :id="album.id"
    />
    <card-album
        v-if="isStock"
        v-for="(album) in albumsFilterd"
        :key="album.id"
        :album="album"
        :id="album.id"
    />
  </main>
</template>
<style scoped>
</style>