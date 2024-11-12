<script setup>
const now = new Date();
  const thisYear = now.getFullYear();
</script>

<template>
  <section className='flex flex-col items-center py-12'>
    <div className='flex items-center mx-auto mb-4'>
      <div className='h-px w-12 bg-gray-400'></div>
      <h3 className='text-sm font-bold text-gray-500 mx-3'>CREATED WITH</h3>
      <div className='h-px w-12 bg-gray-400'></div>
    </div>
    <div className='flex gap-4 justify-center'>
      <img src="@/assets/logo_vue.svg" className='h-7 w-7' alt='vuelogo'></img>
      <img src="@/assets/logo_tailwindcss.svg" className='h-7 w-7' alt='tailwindcsslogo'></img>
      <img src="@/assets/logo_flowbite.svg" className='h-7 w-7' alt='flowbitelogo'></img>
    </div>
  </section>
  <footer className='text-center w-full bg-white'>
    <small>© {{ thisYear }} Glaesses All rights Reserved.</small>
  </footer>
</template>