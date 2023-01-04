<template>
  <div class="home">
    <transition name="toast">
      <Toast v-if="showToast" />
    </transition>
    <Todos @badValue="triggerToast" />
    <div class="container">
      <div class="container">
        <transition name="toggle">
        <div v-if="showP" class="toggle">
          <p>Hello , world </p>
        </div>
        </transition>
        <button @click="showP = !showP">
          Toggle me 
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'
import Toast from '../components/Toast.vue'
import Todos from '../components/Todos.vue'

export default {
  components: { Toast, Todos },
  setup() {
    const showToast = ref(false)
    const showP = ref(false)

    const triggerToast = () => {
      showToast.value = true;
      setTimeout(() => showToast.value = false, 3000)
    }
    
    return { showToast, triggerToast,showP }
  }
}
</script>

<style>
.toggle-enter-from{
  opacity: 0;
}
.toggle-enter-to{
  opacity: 1;
}
.toggle-enter-active{
  transition: all 0.2s ease;
}

.toast-enter-from{
  opacity: O;
  transform: translateY(-60px)
}


.toast-enter-to{
  opacity: 1;
  transform: translateY(0);
}

.toast-enter-active{
  transition: all 0.3s ease;
}

.toast-leave-to{
  opacity: 0;
  transform: translateY(-60px)
}


.toast-leave-from{
  opacity: 1;
  transform: translateY(0);
}

.toast-leave-active{
  transition: all 0.3s ease;
}

</style>
