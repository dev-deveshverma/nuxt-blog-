<script setup>
const { data } = await useFetch(
  "http://192.46.209.205:1337/api/blogs?sort[0]=createdAt%3Adesc&populate=*&pagination[page]=1&pagination[pageSize]=20"
);
console.log("data", data);
</script>
<template>
  <div >
    <div>
      <div
        class="p-10 grid grid-cols-1 sm:grid-cols-1 md:grid-cols-3 lg:grid-cols-3 xl:grid-cols-3 gap-5"
      >
        <!--Card 1-->
        <div
          v-for="{
            attributes: { title, fulltext, featuredimage, catagories, slug },
            id,
          } in data.data"
          :key="id"
          class="rounded overflow-hidden shadow-lg"
        >
          <nuxt-link :to="'/posts/' + slug">
            <img
              class="w-full"
              :src="
                'http://192.46.209.205:1337' +
                featuredimage.data?.attributes.formats.small.url
              "
              alt="Mountain"
            />
            <div class="px-6 py-4">
              <div class="font-bold text-xl mb-2">{{ title.slice(0,40) }}</div>
              <p class="text-gray-700 text-base">
                {{ fulltext.slice(0, 100) }}.....
              </p>
            </div>
            <div class="px-6 pt-4 pb-2">
              <span
                v-for="slug in catagories.data"
                :key="slug.id"
                class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
                >{{ slug.attributes.name }}</span
              >
            </div>
          </nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>
