<script setup>
  import { ref } from 'vue'
  const menus = [
    { name: 'Home', href: 'https://glaesses.net/' },
    { name: 'WebApps', href: 'https://glaesses.net/webapps' }
  ];
  const openMenu = ref(false)
  function setOpenMenu() {
    openMenu.value = !openMenu.value
  }
</script>


<template>
  <header class='flex p-3 pr-8 sm:pr-12 bg-white fixed top-0 w-full z-30 shadow'>
    <div class='flex items-center'>
      <img src="@/assets/logo.png" class='h-12 w-12' alt='logo'></img>
      <h1 class='text-xl font-bold leading-none'>WorkHolic</h1>
    </div>
    <ul class='max-[640px]:hidden flex ml-auto'>
      <li v-for="menu in menus" :key="menu.name" class='flex sm:my-auto sm:ml-6 text-gray-900 rounded hover:bg-gray-100'>
        <a class='p-2 pl-6 sm:pl-2 w-full sm:text-center' :href="menu.href">
          {{menu.name}}
        </a>
      </li>
    </ul>
    <button @click="setOpenMenu" type="button" class="z-30 sm:hidden ml-auto my-auto inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200">
      <svg class="w-6 h-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 1h15M1 7h15M1 13h15"></path>
      </svg>
    </button>
  </header>
  
  <div @click="setOpenMenu" v-if="openMenu" class="fixed top-0 left-0 w-screen h-screen bg-[rgb(0,0,0,0.5)] z-10"></div>
  <ul v-if="openMenu" class="fixed right-0 inset-y-0 flex flex-col gap-2 p-4 pt-28 w-4/5 bg-gray-50 z-10 text-xl font-semibold">
    <li v-for="menu in menus" :key="menu.name" class='flex text-gray-900 rounded hover:bg-gray-100'>
      <a class='p-2 pl-6 w-full' :href="menu.href">
        {{menu.name}}
      </a>
    </li>
    <li>
      <hr class="w-4/5 h-[2px] mx-auto my-4 bg-gray-200 border-0 rounded">
    </li>
  </ul>
</template>