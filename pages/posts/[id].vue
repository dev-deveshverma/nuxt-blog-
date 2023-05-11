<template>
  <div>
    <div
      v-for="{
        attributes: { title, fulltext, createdAt, featuredimage, catagories },
        id,
      } in post"
      :key="id"
      class="max-w-screen-xl mx-auto"
    >
      <main class="mt-10">
        <div
          class="mb-4 md:mb-0 w-full max-w-screen-md mx-auto relative"
          style="height: 24em"
        >
          <div
            class="absolute left-0 bottom-0 w-full h-full z-10"
            style="
              background-image: linear-gradient(
                180deg,
                transparent,
                rgba(0, 0, 0, 0.7)
              );
            "
          ></div>
          <img
            :src="
              'http://192.46.209.205:1337' +
              featuredimage.data?.attributes.formats.small.url
            "
            class="absolute left-0 top-0 w-full h-full z-0 object-cover"
          />
          <div class="p-4 absolute bottom-0 left-0 z-20">
            <a
              href="#"
              v-for="slug in catagories.data"
              :key="slug.id"
              class="px-4 py-1 bg-black text-gray-200 inline-flex items-center justify-center mb-2"
              >{{ slug.attributes.name }}</a
            >
            <h2 class="text-4xl font-semibold text-gray-100 leading-tight">
              {{ title }}
            </h2>
            <div class="flex mt-3">
              <img
                src="https://avatars.githubusercontent.com/u/71995793?v=4"
                class="h-10 w-10 rounded-full mr-2 object-cover"
              />
              <div>
                <p class="font-semibold text-gray-200 text-sm">Devesh Verma</p>
                <p class="font-semibold text-gray-400 text-xs">
                  {{ formatDate(createdAt) }}
                </p>
              </div>
            </div>
          </div>
        </div>
        <div
          class="px-4 lg:px-0 mt-12 text-gray-700 max-w-screen-md mx-auto text-lg leading-relaxed"
        >
          <p class="pb-6">{{ fulltext }}</p>
        </div>
      </main>
    </div>
  </div>
</template>

<script>
import moment from "moment";

export default {
  data() {
    return {
      post: [],
      // baseUrl: process.env.REACT_APP_URL
    };
  },
  methods: {
    formatDate(date) {
      return moment(date).format("MMMM Do YYYY");
    },
  },
  created() {
    fetch(
      `http://192.46.209.205:1337/api/blogs?filters[slug][$eq]=${this.$route.params.id}&populate=*`
    )
      .then((response) => response.json())
      .then((data) => {
        this.post = data.data;
        console.log("data", data.data);
      });
  },
};
</script>

<style lang="sass" scoped></style>
