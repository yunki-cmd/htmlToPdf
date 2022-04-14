<template>
  <article>
    <section>
      <div :id="item" class="flex flex-wrap"  v-for="item in urlImages" :key="item">
        <div class="overflow-visible resize relative">
          <img :src="item" class="w-full h-full">
        </div>
      </div>
    </section>
  </article>
</template>

<script>
import {reactive,computed} from "vue"

export default {
  name:'Cards',
  props:{
    images:{
      type:Array
    }
  },
  setup(props){
    const observer = new MutationObserver(function(mutations) {
      console.log(mutations)
      console.log('Resized')
    })

    const urlImages = computed(()=>{
      return props.images.map(element=>{
        return previm(element)
      })
    })

    const previm = (item) =>{
        const s =  window.URL.createObjectURL(item)
        return s
      }
    const dimensinar = (e) =>{
      /* urlImages.value.forEach(element => {
        console.log(element)
        let n = document.getElementById(element)
        observer.observe(n, { attributes: true });
      }); */
      console.log(e.target)
    }
    return {props,previm,urlImages, dimensinar}
  }

}
</script>

<style>

</style>