<template>
  <div class="flex justify-center">
  <div class="mb-3 w-96">
    <label for="formFileMultiple" class="form-label inline-block mb-2 text-gray-700">Multiple files input example</label>
    <input ref="selectImg" @change="imprimir" class="form-control
    block
    w-full
    px-3
    py-1.5
    text-base
    font-normal
    text-gray-700
    bg-white bg-clip-padding
    border border-solid border-gray-300
    rounded
    transition
    ease-in-out
    m-0
    focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none" type="file" id="formFileMultiple" multiple>
  </div>
</div>

</template>

<script>
import {ref} from "vue"

export default {
   emits: ['prueba'],
  setup(props, {emit}){
    const selectImg = ref()

    console.log(selectImg.value)
    const imprimir = (e) =>{
      emit("prueba", e.target.files)
    }

    return {selectImg, imprimir}
  }
}
</script>

<style>

</style>