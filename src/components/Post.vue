<script setup>
  import {
    ChatBubbleLeftIcon,
    ArrowPathRoundedSquareIcon,
    HeartIcon,
    ChartBarIcon,
    ArrowUpTrayIcon,
    EllipsisHorizontalIcon
  } from '@heroicons/vue/24/outline'

  defineProps({
    id: {
      type: String,
      required: true
    },
    author_name: {
      type: String,
      required: true
    },
    author_id: {
      type: String,
      required: true
    },
    author_icon: {
      type: String,
      required: true
    },
    date: {
      type: String,
      required: true
    },
    content: {
      type: String,
      required: true
    },
    medias: {
      type: Array,
      required: false
    },
    comments: {
      type: String,
      required: false
    },
    reposts: {
      type: String,
      required: false
    },
    likes: {
      type: String,
      required: false
    },
    views: {
      type: String,
      required: false
    }
  })
</script>

<template>
  <router-link :to="'/' + author_id + '/status/' + id" class="text-left">
    <div class="relative flex flex-row px-4 py-3 border-b border-b-slate-100 hover:bg-gray-100 transition hover:transition">
      <router-link :to="'/' + author_id" class="h-full">
        <div class="w-12">
          <img :src="author_icon" alt="Profile picture" class="w-12 h-12 rounded-full hover:filter hover:brightness-90 transition hover:transition" />
        </div>
      </router-link>
      <div class="ps-3 w-full">
        <div class="flex flex-row justify-between">
          <div>
            <router-link :to="'/' + author_id">
              <h1 class="inline font-semibold hover:underline hover:decoration-2">{{ author_name }}</h1>
            </router-link>
            <p class="inline text-slate-500 ms-2">@{{ author_id }} • {{ date }}</p>
          </div>
          <div>
            <button class="absolute top-2 right-2 text-sm text-slate-500 p-1 rounded-full hover:bg-sky-200 hover:text-sky-500 transition hover:transition">
              <EllipsisHorizontalIcon class="w-6" />
            </button>
          </div>
        </div>
        <div class="whitespace-pre-line font-sans leading-tight">{{ content }}</div>
        
        <div v-if="medias && medias.length === 1" class="rounded-xl border border-gray-300 mt-3">
          <img :src="medias[0]" alt="Media" class="rounded-xl" />
        </div>
        
        <div v-if="medias && medias.length > 1" class="grid grid-cols-2 grid-rows-2 gap-0.5 rounded-xl border border-gray-300 mt-3 aspect-video">

          <div v-if="medias.length === 2" v-for="(media,index) in medias" :class="'row-span-2 ' + (index === 0 ? 'rounded-l-xl' : 'rounded-r-xl')">
            <img :src="media" alt="Media" :class="'h-full w-full object-cover ' + (index === 0 ? 'rounded-l-xl' : 'rounded-r-xl')" />
          </div>

          <div v-if="medias.length === 3" v-for="(media,index) in medias" :class="(index === 0 ? 'row-span-2 rounded-l-xl' : (index === 1 ? 'rounded-tr-xl' : 'rounded-br-xl'))">
            <img :src="media" alt="Media" :class="'h-full w-full object-cover ' + (index === 0 ? 'rounded-l-xl' : (index === 1 ? 'rounded-tr-xl' : 'rounded-br-xl'))" />
          </div>

          <div v-if="medias.length === 4" v-for="(media,index) in medias" :class="(index === 0 ? 'rounded-tl-xl' : (index === 1 ? 'rounded-tr-xl' : (index === 2 ? 'rounded-bl-xl' : 'rounded-br-xl')))">
            <img :src="media" alt="Media" :class="'h-full w-full object-cover ' + (index === 0 ? 'rounded-tl-xl' : (index === 1 ? 'rounded-tr-xl' : (index === 2 ? 'rounded-bl-xl' : 'rounded-br-xl')))" />
          </div>

        </div>
        <div class="flex flex-row justify-between mt-3">
          <div class="flex flex-row text-slate-500 hover:text-cyan-500">
            <ChatBubbleLeftIcon class="w-5 h-5" />
            <div class="ms-2 text-sm">{{ comments }}</div>
          </div>
          <div class="flex flex-row text-slate-500 hover:text-green-500">
            <ArrowPathRoundedSquareIcon class="w-5 h-5" />
            <div class="ms-2 text-sm">{{ reposts }}</div>
          </div>
          <div class="flex flex-row text-slate-500 hover:text-pink-500">
            <HeartIcon class="w-5 h-5" />
            <div class="ms-2 text-sm">{{ likes }}</div>
          </div>
          <div class="flex flex-row text-slate-500 hover:text-cyan-500">
            <ChartBarIcon class="w-5 h-5" />
            <div class="ms-2 text-sm">{{ views }}</div>
          </div>
          <div class="flex flex-row text-slate-500 hover:text-cyan-500">
            <ArrowUpTrayIcon class="w-5 h-5" />
          </div>
        </div>
      </div>
    </div>
  </router-link>
</template>
