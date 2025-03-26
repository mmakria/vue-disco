<script setup>
import OutStockSvg from "@/components/utils/OutStockSvg.vue";
import InStockSvg from "@/components/utils/InStockSvg.vue";
import ButtonStock from "@/components/utils/ButtonStock.vue";
import CardLayout from "@/components/CardLayout.vue";

const props = defineProps({
  album: Object,
  isStock: Boolean
})

const incrementStock = () => {
  props.album.stock++
}
const decrementStock = () => {
  if (props.album.stock > 0) {
    props.album.stock--
  }
}
</script>

<template>
  <card-layout
  >
    <div class="sm:w-44 sm:h-44 lg:w-40 lg:h-40 sm:mr-10 inline-flex items-center justify-center flex-shrink-0">
      <img :src="album?.coverUrl ? album.coverUrl : 'src/assets/img/default.jpg'" alt="cover-album">
    </div>
    <div class="flex-grow sm:text-left text-center mt-6 sm:mt-0">
      <h1 class="text-black text-2xl title-font font-bold mb-2">{{ album.title }}</h1>
      <h3 class="text-black text-xl title-font mb-2">{{ album.artist }}<span
          class="font-light mr-2"> {{ album.year }}</span>
      </h3>
      <p class="leading-relaxed text-base">{{
          album.comment
        }}</p>
      <div class="py-4">
        <div v-if="album.stock >= 1" class=" inline-block mr-2"> <!-- quand le stock est ok  -->
          <div class="flex  pr-2 h-full items-center">
            <InStockSvg/>
            <p class="title-font font-medium">{{ album.stock }} stock</p>
          </div>
        </div>
        <div v-if="album.stock < 1" class="inline-block mr-2"><!-- quand le stock est à zéro  -->
          <div class="flex pr-2 h-full items-center">
            <OutStockSvg/>
            <p class="title-font font-medium">out of stock</p>
          </div>
        </div>
      </div>
      <div class="md:flex font-bold text-gray-800">
        <div class="w-full md:w-1/2 flex space-x-3">
          <div>
            <p>pitchfork pos : #{{ album.pitchforkPos }}</p><!-- pitchfork pos  -->
          </div>
        </div>
        <div class="w-full">
          <div class="float-right">
            <ButtonStock
                @decrement="decrementStock "
                @increment="incrementStock"
            />
          </div>
        </div>
      </div>
    </div>
  </card-layout>
</template>

<style scoped>

</style>