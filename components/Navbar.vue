<template>
  <nav class="bg-gray-800">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <div class="flex-shrink-0">
          <NuxtLink to="/" class="flex items-center">
            <img
              class="h-8 w-auto"
              src=" https://api.iconify.design/bxl:blogger.svg?color=%23ffffff"
              alt="Logo"
            />

            <span class="text-white ml-2 font-bold">My Blog</span>
          </NuxtLink>
        </div>
        <div class="hidden md:block">
          <div class="ml-4 flex items-center md:ml-6">
            <NuxtLink
              to="/"
              class="text-gray-300 hover:text-white px-3 py-2 rounded-md text-sm font-medium"
              >Home</NuxtLink
            >
            <NuxtLink
              to="/About"
              class="text-gray-300 hover:text-white px-3 py-2 rounded-md text-sm font-medium"
              >About</NuxtLink
            >
            <NuxtLink
              to="/contact"
              class="text-gray-300 hover:text-white px-3 py-2 rounded-md text-sm font-medium"
              >Contact</NuxtLink
            >
          </div>
        </div>
        <div class="-mr-2 flex md:hidden">
          <button
            type="button"
            @click="isOpen = !isOpen"
            class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:bg-gray-700 focus:text-white transition duration-150 ease-in-out"
          >
            <svg
              :class="{ hidden: isOpen, block: !isOpen }"
              class="h-6 w-6"
              stroke="currentColor"
              fill="none"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              ></path>
            </svg>
            <svg
              :class="{ hidden: !isOpen, block: isOpen }"
              class="h-6 w-6"
              stroke="currentColor"
              fill="none"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              ></path>
            </svg>
          </button>
        </div>
      </div>
    </div>
    <div :class="{ block: isOpen, hidden: !isOpen }" class="hidden md:hidden">
      <div class="px-2 pt-2 pb-3 sm:px-3">
        <NuxtLink
          to="/"
          class="text-gray-300 hover:text-white block px-3 py-2 rounded-md text-base font-medium"
          >Home</NuxtLink
        >
        <NuxtLink
          to="/Blog"
          class="text-gray-300 hover:text-white block px-3 py-2 rounded-md text-base font-medium"
          >Blog</NuxtLink
        >
        <NuxtLink
          to="/About"
          class="text-gray-300 hover:text-white block px-3 py-2 rounded-md text-base font-medium"
          >About</NuxtLink
        >
        <NuxtLink
          to="/contact"
          class="text-gray-300 hover:text-white block px-3 py-2 rounded-md text-base font-medium"
          >Contact</NuxtLink
        >
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  setup() {
    return {};
  },
};
</script>

<style lang="scss" scoped></style>
