<template>
  <!-- <header class="sticky top-0 flex justify-center py-6 bg-green-900 place-items-center">
    <img alt="Vue logo" src="../assets/logo.png" width="32" />
    <span class="ml-4 text-lg font-bold text-green-100 md:text-xl">
      Vue News | NYTimes Edition
    </span>
  </header> -->
  <nav class="fixed w-full top-0 z-50 flex items-center justify-between flex-wrap bg-yellow-50 p-6 pl-5">
    <div class="flex items-center flex-no-shrink text-black ml-10">
      <a href="./Home.vue"><img src="../assets/logo.png" alt="" class="fill-current" width="32"></a>
    </div>
    <div class="block sm:hidden">
      <button @click="toggle" class="flex items-center px-3 py-2 border rounded text-black border-yellow-900 hover:text-yellow-900 hover:border-black">
        <svg class="fill-current h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><title>Menu</title><path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"/></svg>
      </button>
    </div>
    <div :class="open ? 'block': 'hidden'" class="w-full mr-10 sm:flex sm:items-center sm:w-auto">
      <div class="text-lg font-semibold sm:flex-grow">
        <a href="#" class="no-underline block mt-4 sm:inline-block sm:mt-0 hover:text-yellow-900 mr-4">
          Home
        </a>
        <a href="#" class="no-underline block mt-4 sm:inline-block sm:mt-0 hover:text-yellow-900 mr-4">
          Categories
        </a>
        <a href="#" class="no-underline block mt-4 sm:inline-block sm:mt-0 hover:text-yellow-900">
          Random
        </a>
        <transition name="fade" mode="out-in">
           <router-view/>
        </transition>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Nav', 
  data(){
    return {
      open: false
    }
  },
  methods: {
    toggle() {
      this.open = !this.open
    }
  }
    
}
</script>