<script setup>
  defineProps({
    to: {
      type: String,
      required: true
    },
    name: {
      type: String,
      required: true
    }
  })
</script>

<template>
  <li class="flex justify-center xl:justify-start">
    <router-link :to="to" activeClass="font-bold">
      <div class="flex flex-row w-max rounded-full text-xl p-3 xl:px-5 xl:py-2.5 hover:bg-gray-200 transition hover:transition">
        <slot v-if="!isRouteActive(to)" name="outlineIcon"></slot>
        <slot v-else name="solidIcon"></slot>
        <div class="ms-5 hidden xl:block">
          {{ name }}
        </div>
      </div>
    </router-link>
  </li>
</template>

<script>
  export default {
    methods: {
      isRouteActive(route) {
        return this.$route.path === route
      }
    }
  }
</script>
