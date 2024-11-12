<script>
export default {
  emits: ['set-show'],
}
</script>

<template>
  <div class="fixed top-0 left-0 w-screen h-screen bg-[rgb(0,0,0,0.5)] z-30"></div>
  <div class="overflow-y-auto overflow-x-hidden fixed top-[20px] right-0 left-0 z-50 flex justify-center items-center w-full md:inset-0 h-[calc(100%-40px)] max-h-full">
    <div class="relative p-4 w-full max-w-2xl max-h-full">
      <div class="relative bg-white rounded-lg shadow">
        <div class="flex items-center justify-between p-4 md:p-5 border-b rounded-t">
          <h3 class="text-xl font-semibold text-gray-900">
            <slot name="header"></slot>
          </h3>
          <button @click="$emit('set-show')" type="button" class="text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 rounded-lg text-sm w-8 h-8 ms-auto inline-flex justify-center items-center">
            <svg class="w-3 h-3" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 14">
              <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m1 1 6 6m0 0 6 6M7 7l6-6M7 7l-6 6"/>
            </svg>
          </button>
        </div>
        <div class="p-4 md:p-5 space-y-4 text-sm leading-relaxed text-gray-500">
          <slot name="detail"></slot>
        </div>
        <div class="flex items-center p-4 md:p-5 border-t border-gray-200 rounded-b">
          <!-- <button type="button" class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center">OK</button> -->
        </div>
      </div>
    </div>
  </div>
</template>