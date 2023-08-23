<template>
  <div class="p-4">
    <router-link to="/tos" class="text-slate-500 text-sm me-3 hover:underline">{{ $t('home.terms_of_service') }}</router-link>
    <router-link to="/privacy" class="text-slate-500 text-sm me-3 hover:underline">{{ $t('home.privacy_policy') }}</router-link>
    <router-link to="/cookies" class="text-slate-500 text-sm me-3 hover:underline">{{ $t('home.cookie_policy') }}</router-link>
    <router-link to="/accessibility" class="text-slate-500 text-sm me-3 hover:underline">{{ $t('home.accessibility') }}</router-link>
    <router-link to="/ads" class="text-slate-500 text-sm me-3 hover:underline">{{ $t('home.ads_info') }}</router-link>
    <button class="text-slate-500 text-sm me-3 hover:underline">{{ $t('home.more') }}</button>
  </div>
</template>
