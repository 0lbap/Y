<script setup>
  import posts from '../data/posts.json'
  import trends from '../data/trends.json'
  import suggestions from '../data/suggestions.json'

  import Post from '../components/Post.vue'
  import Trend from '../components/Trend.vue'
  import Suggestion from '../components/Suggestion.vue'
  import Footer from '../components/Footer.vue'

  import {
    PhotoIcon,
    GifIcon,
    ListBulletIcon,
    FaceSmileIcon,
    CalendarDaysIcon,
    MapPinIcon,
    MagnifyingGlassIcon
  } from '@heroicons/vue/24/outline'
</script>

<template>

  <main class="inline-block align-top h-full w-10/12 lg:w-7/12 xl:w-5/12 border border-transparent border-l-slate-100 lg:border-r-slate-100 overflow-y-auto">

    <h1 class="text-xl font-bold p-3">{{ $t('home.home') }}</h1>

    <div class="flex flex-row border-b border-b-slate-100">
      <button class="basis-1/2 font-semibold py-4 hover:bg-gray-200 transition hover:transition">
        <span class="inline w-max border-b-4 border-b-sky-500 pb-3">{{ $t('home.for_you') }}</span>
      </button>
      <button class="basis-1/2 font-semibold py-4 hover:bg-gray-200 transition hover:transition">
        <span class="inline w-max text-slate-500">{{ $t('home.subscriptions') }}</span>
      </button>
    </div>
    
    <div class="flex flex-row px-4 py-3 border-b border-b-slate-100">
      <router-link to="/that_cat">
        <div class="w-12">
          <img src="https://cdn.pixabay.com/photo/2018/05/14/21/43/british-shorthair-3401683_1280.jpg" alt="Profile picture" class="rounded-full hover:filter hover:brightness-90 transition hover:transition" />
        </div>
      </router-link>
      <div class="w-full ps-3">
        <input class="text-xl w-full mt-2 mb-5 ms-2" type="text" :placeholder="$t('home.what_is_happening')" />
        <div class="flex flex-row justify-between">
          <div class="flex flex-row justify-between">
            <button class="p-2 rounded-full hover:bg-sky-100 text-sky-500 disabled:bg-transparent disabled:text-sky-300 transition hover:transition"><PhotoIcon class="w-6 h-6" /></button>
            <button class="p-2 rounded-full hover:bg-sky-100 text-sky-500 disabled:bg-transparent disabled:text-sky-300 transition hover:transition"><GifIcon class="w-6 h-6" /></button>
            <button class="hidden sm:block p-2 rounded-full hover:bg-sky-100 text-sky-500 disabled:bg-transparent disabled:text-sky-300 transition hover:transition"><ListBulletIcon class="w-6 h-6" /></button>
            <button class="p-2 rounded-full hover:bg-sky-100 text-sky-500 disabled:bg-transparent disabled:text-sky-300 transition hover:transition"><FaceSmileIcon class="w-6 h-6" /></button>
            <button class="hidden sm:block p-2 rounded-full hover:bg-sky-100 text-sky-500 disabled:bg-transparent disabled:text-sky-300 transition hover:transition"><CalendarDaysIcon class="w-6 h-6" /></button>
            <button class="p-2 rounded-full hover:bg-sky-100 text-sky-500 disabled:bg-transparent disabled:text-sky-300 transition hover:transition" disabled><MapPinIcon class="w-6 h-6" /></button>
          </div>
          <button class="px-4 my-0.5 text-white rounded-full font-semibold bg-sky-500 hover:bg-sky-600 disabled:bg-sky-300" disabled>{{ $t('buttons.post') }}</button>
        </div>
      </div>
    </div>

    <Post
      v-for="post in posts.posts"
      :id="post.id"
      :author_name="post.author_name"
      :author_id="post.author_id"
      :author_icon="post.author_icon"
      :date="post.date"
      :content="post.content"
      :medias="post.medias"
      :comments="post.comments"
      :reposts="post.reposts"
      :likes="post.likes"
      :views="post.views"
    />
    
  </main>

  <nav class="hidden lg:inline-block align-top h-full w-4/12 px-8 overflow-y-auto">

    <div class="relative w-full mt-2 mb-4">
      <MagnifyingGlassIcon class="absolute w-6 m-3 ms-4 text-gray-400" />
      <input type="search" class="w-full p-3 ps-12 bg-gray-100 rounded-full focus:bg-white accent-sky-600" :placeholder="$t('home.search')"/>
    </div>

    <div class="bg-gray-100 rounded-2xl p-4 mb-4">
      <h1 class="pb-2 text-xl font-extrabold">{{ $t('home.subscribe_to_premium') }}</h1>
      <p class="font-bold mb-4 leading-tight">{{ $t('home.subscribe_to_premium_desc') }}</p>
      <router-link to="/verified" class="px-4 py-2 text-white rounded-full font-semibold bg-slate-900 hover:bg-slate-800">{{ $t('buttons.subscribe') }}</router-link>
    </div>

    <div class="bg-gray-100 rounded-2xl mb-4">
      <h1 class="p-4 pb-2 text-xl font-extrabold">{{ $t('home.trends_for_you') }}</h1>
      <Trend
        v-for="trend in trends.trends"
        :name="trend.name"
        :type="trend.type"
        :posts="trend.posts"
      />
      <router-link to="/trends">
        <div class="px-4 py-3 text-sky-500 rounded-b-2xl hover:bg-gray-200 transition hover:transition">
          {{ $t('buttons.show_more') }}
        </div>
      </router-link>
    </div>

    <div class="bg-gray-100 rounded-2xl">
      <h1 class="p-4 pb-2 text-xl font-extrabold">{{ $t('home.who_to_follow') }}</h1>
      <Suggestion
        v-for="suggestion in suggestions.suggestions"
        :user_name="suggestion.user_name"
        :user_id="suggestion.user_id"
        :user_icon="suggestion.user_icon"
      />
      <router-link to="/trends">
        <div class="px-4 py-3 text-sky-500 rounded-b-2xl hover:bg-gray-200 transition hover:transition">
          {{ $t('buttons.show_more') }}
        </div>
      </router-link>
    </div>

    <Footer />
    
    <div class="h-20"></div>

  </nav>
  
</template>
