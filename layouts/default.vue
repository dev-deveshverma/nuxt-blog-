<template>
  <div class="flex flex-col h-screen justify-between" >
    <Navbar />
    <slot />
    <section-recent-blog/>
  </div>
</template>

<script>
import SectionRecentBlog from '~/components/Footer.vue';
export default {
  components: { SectionRecentBlog },};
</script>

<style scoped></style>
