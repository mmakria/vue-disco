<script setup>
import CardAlbum from "@/components/CardAlbum.vue";
import {records} from '/src/assets/js/allRecords'
import {ref, computed} from "vue";

const albums = ref(records)
const props = defineProps({
  isStock: Boolean,
  isSelected: String
})

const filteredAlbums = computed(() => {
  if (props.isStock) {
    albums.value = albums.value.filter((album) => album.stock > 0)
  } else {
    albums.value = records
  }

  if (props.isSelected === "pitchforpros") {
    console.log("pitch")
    albums.value = albums.value.sort((a, b) => b.pitchforkPos - a.pitchforkPos)
  } else if (props.isSelected === "year") {
    console.log("year")
    albums.value = albums.value.sort((a, b) => b.year - a.year)
  } else {
    console.log("all")
  }
  return albums.value
})


</script>

<template>


  <main class="bg-white py-5 ml-6 basis-auto">
    <card-album
        v-for="(album) in filteredAlbums"
        :key="album.id"
        :album="album"
        :id="album.id"
    />

  </main>
</template>
<style scoped>
</style>