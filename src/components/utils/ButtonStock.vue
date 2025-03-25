<script setup>
const emits = defineEmits(["increment", "decrement"])

const handleButtonInc = () => {
  emits("increment")
}

const handleButtonDec = () => {
  emits("decrement")
}
</script>

<template>
  <button @click="handleButtonInc"
          type="button"
          class="border border-teal-500 bg-teal-500 text-white rounded-md px-4 py-2 m-2 ease select-none hover:bg-teal-400">
    +
  </button>
  <button @click="handleButtonDec"
          type="button"
          class="border border-teal-500 bg-teal-500 text-white rounded-md px-4 py-2 m-2 ease select-none hover:bg-purple-800">
    -
  </button>
</template>

<style scoped>

</style>