<template>
  <nav class="bg-gray-800">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <div class="flex-shrink-0">
          <NuxtLink to="/" class="flex items-center">
            <svg
              class="h-8 w-auto"
              xmlns="http://www.w3.org/2000/svg"
              width="1em"
              height="1em"
              viewBox="0 0 24 24"
            >
              <path
                fill="#ffffff"
                d="M20.954 10.667c-.072-.322-.272-.621-.502-.745c-.07-.039-.522-.088-1.004-.109c-.809-.036-.898-.052-1.152-.201c-.405-.237-.516-.493-.518-1.187c-.002-1.327-.554-2.559-1.646-3.67c-.776-.793-1.645-1.329-2.634-1.629c-.236-.072-.768-.097-2.545-.118c-2.787-.033-3.405.024-4.356.402c-1.748.697-3.008 2.166-3.465 4.05c-.087.353-.103.92-.124 4.177c-.025 4.08.004 4.68.258 5.488c.212.668.425 1.077.861 1.657c.835 1.108 2.083 1.907 3.334 2.133c.595.107 7.931.135 8.683.032c1.306-.178 2.331-.702 3.293-1.684c.694-.71 1.129-1.479 1.414-2.499c.117-.424.127-.63.149-3.117c.017-1.878.002-2.758-.046-2.98zM8.007 8.108c.313-.316.399-.329 2.364-.329c1.764 0 1.822.004 2.081.134c.375.189.538.456.538.88c0 .384-.153.653-.493.869c-.184.115-.293.123-2.021.133c-1.067.007-1.916-.013-2.043-.048c-.669-.184-.918-1.143-.426-1.639zm7.706 8.037l-.597.098l-3.114.035c-2.736.033-3.511-.018-3.652-.08c-.288-.124-.554-.472-.602-.78c-.042-.292.104-.696.33-.9c.285-.257.409-.266 3.911-.27c3.602-.002 3.583-.003 3.925.315c.482.45.381 1.251-.201 1.582z"
              ></path>
            </svg>

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
