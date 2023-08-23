<template>
  <main class="inline-block align-top h-full w-10/12 lg:w-11/12 xl:w-9/12 text-center pt-20">
    <p class="text-gray-500 mb-10 ">{{ $t('page_not_found') }}</p>
    <router-link to="/search" class="rounded-full font-bold px-4 py-2 text-white bg-sky-500 hover:bg-sky-600">{{ $t('buttons.search') }}</router-link>
  </main>
</template>
