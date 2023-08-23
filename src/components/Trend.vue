<script setup>
  import { EllipsisHorizontalIcon } from '@heroicons/vue/24/outline'

  defineProps({
    name: {
      type: String,
      required: true
    },
    type: {
      type: String,
      required: true
    },
    posts: {
      type: String,
      required: true
    }
  })
</script>

<template>
  <router-link to="/search">
    <div class="px-4 py-3 pt-2 hover:bg-gray-200 transition hover:transition">
      <div class="flex flex-row justify-between">
        <p class="text-sm text-slate-500 pt-1">{{ $t('trends.' + type) }} • {{ $t('trends.trends') }}</p>
        <button class="text-sm text-slate-500 p-1 rounded-full hover:bg-sky-200 hover:text-sky-500 transition hover:transition">
          <EllipsisHorizontalIcon class="w-6" />
        </button>
      </div>
      <h1 class="font-semibold">{{ name }}</h1>
      <p class="text-sm text-slate-500">{{ posts }} {{ $t('trends.posts') }}</p>
    </div>
  </router-link>
</template>
