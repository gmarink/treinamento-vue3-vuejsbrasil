<template>
  <teleport
  to="body"
  >
  <div class="fixed top-0 left-0 z-50 flex items-center justify-center w-full bg-black bg-opacity-50"
  >
 <div class="fixed mx-10">
 <div class="flex flex-col overflow-hidden bg-white rounded-lg animate__animated animate__fadeInDown animate__faster">
 <div class="flex flex-col px-12 py-10 bg-white"
 >
 <component :is="state.component" />
 </div>
 </div>
 </div>
  </div>
  </teleport>
</template>

<script>
import { reactive } from '@vue/reactivity'
export default {
    setup () {
        const state = reactive({
            
        })
    }

}
</script>

<style>

</style>