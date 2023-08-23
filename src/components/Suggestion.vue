<script setup>
  defineProps({
    user_name: {
      type: String,
      required: true
    },
    user_id: {
      type: String,
      required: true
    },
    user_icon: {
      type: String,
      required: true
    }
  })
</script>

<template>
  <router-link :to="'/' + user_id">
    <div class="flex flex-row px-4 py-3 hover:bg-gray-200 transition hover:transition">
      <div class="w-12">
        <img :src="user_icon" alt="Profile picture" class="rounded-full hover:filter hover:brightness-90 transition hover:transition" />
      </div>
      <div class="w-1/2 mx-3">
        <h1 class="font-semibold hover:underline hover:decoration-2 truncate">{{ user_name }}</h1>
        <p class="text-slate-500 truncate">@{{ user_id }}</p>
      </div>
      <div class="ms-auto flex flex-col justify-center">
        <button class="px-4 py-1 text-sm text-white rounded-full font-semibold bg-slate-900 hover:bg-slate-800">{{ $t('buttons.follow') }}</button>
      </div>
    </div>
  </router-link>
</template>
