<script setup>
  import SideNavItem from './SideNavItem.vue'

  import {
    HomeIcon as HomeIconOutline,
    MagnifyingGlassIcon as MagnifyingGlassIconOutline,
    BellIcon as BellIconOutline,
    EnvelopeIcon as EnvelopeIconOutline,
    DocumentTextIcon as DocumentTextIconOutline,
    BookmarkIcon as BookmarkIconOutline,
    UsersIcon as UsersIconOutline,
    CheckBadgeIcon as CheckBadgeIconOutline,
    UserIcon as UserIconOutline,
    EllipsisHorizontalCircleIcon,
    EllipsisHorizontalIcon
  } from '@heroicons/vue/24/outline'

  import {
    HomeIcon as HomeIconSolid,
    BellIcon as BellIconSolid,
    EnvelopeIcon as EnvelopeIconSolid,
    DocumentTextIcon as DocumentTextIconSolid,
    BookmarkIcon as BookmarkIconSolid,
    UsersIcon as UsersIconSolid,
    CheckBadgeIcon as CheckBadgeIconSolid,
    UserIcon as UserIconSolid,
    PencilIcon
  } from '@heroicons/vue/24/solid'
</script>

<template>
  <nav class="inline-block align-top w-2/12 lg:w-1/12 xl:w-3/12 h-full px-4 xl:px-8 pb-3 overflow-hidden">
    <div class="h-full flex flex-col justify-between">
      <ul class="text-center xl:text-left">
        <li class="mb-3 flex justify-center xl:justify-start">
          <router-link to="/home" class="rounded-full text-4xl font-bold p-0 lg:px-3 xl:px-4 xl:py-2 hover:bg-gray-200 transition hover:transition">𝕐</router-link>
        </li>
        <SideNavItem to="/home" :name="$t('sidenav.home')" >
          <template #outlineIcon>
            <HomeIconOutline class="w-6" />
          </template>
          <template #solidIcon>
            <HomeIconSolid class="w-6" />
          </template>
        </SideNavItem>
        <SideNavItem to="/explore" :name="$t('sidenav.explore')" >
          <template #outlineIcon>
            <MagnifyingGlassIconOutline class="w-6" />
          </template>
          <template #solidIcon>
            <MagnifyingGlassIconOutline class="w-6 stroke-2" />
          </template>
        </SideNavItem>
        <SideNavItem to="/notifications" :name="$t('sidenav.notifications')" >
          <template #outlineIcon>
            <BellIconOutline class="w-6" />
          </template>
          <template #solidIcon>
            <BellIconSolid class="w-6" />
          </template>
        </SideNavItem>
        <SideNavItem to="/messages" :name="$t('sidenav.messages')" >
          <template #outlineIcon>
            <EnvelopeIconOutline class="w-6" />
          </template>
          <template #solidIcon>
            <EnvelopeIconSolid class="w-6" />
          </template>
        </SideNavItem>
        <SideNavItem to="/lists" :name="$t('sidenav.lists')" >
          <template #outlineIcon>
            <DocumentTextIconOutline class="w-6" />
          </template>
          <template #solidIcon>
            <DocumentTextIconSolid class="w-6" />
          </template>
        </SideNavItem>
        <SideNavItem to="/bookmarks" :name="$t('sidenav.bookmarks')" >
          <template #outlineIcon>
            <BookmarkIconOutline class="w-6" />
          </template>
          <template #solidIcon>
            <BookmarkIconSolid class="w-6" />
          </template>
        </SideNavItem>
        <SideNavItem to="/communities" :name="$t('sidenav.communities')" >
          <template #outlineIcon>
            <UsersIconOutline class="w-6" />
          </template>
          <template #solidIcon>
            <UsersIconSolid class="w-6" />
          </template>
        </SideNavItem>
        <SideNavItem to="/verified" :name="$t('sidenav.verified')" >
          <template #outlineIcon>
            <CheckBadgeIconOutline class="w-6" />
          </template>
          <template #solidIcon>
            <CheckBadgeIconSolid class="w-6" />
          </template>
        </SideNavItem>
        <SideNavItem to="/that_cat" :name="$t('sidenav.profile')" >
          <template #outlineIcon>
            <UserIconOutline class="w-6" />
          </template>
          <template #solidIcon>
            <UserIconSolid class="w-6" />
          </template>
        </SideNavItem>
        <li class="flex justify-center xl:justify-start">
          <button>
            <div class="flex flex-row w-max rounded-full text-xl p-3 xl:px-5 xl:py-2.5 hover:bg-gray-200 transition hover:transition">
              <EllipsisHorizontalCircleIcon class="w-6" />
              <div class="ms-5 hidden xl:block">
                {{ $t('sidenav.more') }}
              </div>
            </div>
          </button>
        </li>
        <li class="flex justify-center xl:justify-start">
          <button class="hidden xl:block w-full mt-2 py-3.5 rounded-full text-white font-bold shadow-xl bg-sky-500 hover:bg-sky-600 transition hover:transition">
            {{ $t('buttons.post') }}
          </button>
          <button class="xl:hidden mt-2 p-3 rounded-full text-white font-bold shadow-xl bg-sky-500 hover:bg-sky-600 transition hover:transition">
            <PencilIcon class="w-6" />
          </button>
        </li>
      </ul>
      <button class="flex flex-row justify-center xl:justify-start">
        <div class="flex flex-row justify-center w-max xl:w-full p-2 xl:px-4 xl:py-3 rounded-full hover:bg-gray-200 transition text-left hover:transition">
          <div class="align-middle w-12">
            <img src="https://cdn.pixabay.com/photo/2018/05/14/21/43/british-shorthair-3401683_1280.jpg" alt="Profile picture" class="rounded-full" />
          </div>
          <div class="hidden xl:inline-block align-middle w-4/6 ps-3">
            <h1 class="font-semibold text-left">that cat tho :3</h1>
            <p class="text-slate-500 text-left">@that_cat</p>
          </div>
          <div class="hidden xl:flex xl:flex-row xl:justify-end w-1/6">
            <EllipsisHorizontalIcon class="w-6" />
          </div>
        </div>
      </button>
    </div>
  </nav>
</template>
