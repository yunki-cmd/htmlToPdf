<template>
  <Seleccionar @prueba="prueba"/>
  <Cards :images="datos.files" />
</template>

<script >
import Seleccionar from "@/components/seleccionar.vue"
import Cards from "@/components/cards.vue"
import { reactive } from "vue"
  export default {
    setup(){
      const datos = reactive({
        files : []
      })
      const prueba = ("prueba", (data)=>{
        datos.files = []
       for (const key in data) {
          if(Object.hasOwnProperty.call(data, key)){
            datos.files.push(data[key])
          }
        }
      })

      return {prueba,datos,}
    },
    components:{
      Seleccionar,
      Cards
    }
  }

</script>
