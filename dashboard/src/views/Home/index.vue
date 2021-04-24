<template>
<div>
  <custom-header
    @create-account="handlerAccountCreate"
    @login="handlerLogin"
  />
  <contact />
  <div class="flex justify-center py-10 bg-brand-gray">
    <p class="font-medium text-center text-gray-800">feedbacker &copy; 2021</p>
  </div>
</div>
</template>

<script>
import { onMounted } from 'vue'
import { useRouter } from 'vue-router'
import Contact from './Contact.vue'
import CustomHeader from './CustomHeader'
import useModal from '../../hooks/useModal'

export default {
  components: { Contact, CustomHeader },
  setup () {
    const router = useRouter()
    const modal = useModal()
    onMounted(() => {
      const token = window.localStorage.getItem('token')
      if (token) {
        router.push({ name: 'Feedback' })
      }
    })
    function handlerLogin () {
      modal.open({
        component: 'ModalLogin'
      })
    }
    function handlerAccountCreate () { 
      modal.open({
        component: 'ModalCreateAccount'
      })
    }
    return {
      handlerLogin,
      handlerAccountCreate
    }
  }
}
</script>
