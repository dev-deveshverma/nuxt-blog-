<template>
  <div>
    {{ this.$route.params.id }}
  </div>
</template>

<script>
export default {
  data() {
    return {
      postData: [],
    };
  },
  created() {
    fetch(
      `http://192.46.209.205:1337/api/blogs?filters[slug][$eq]=${this.$route.params.id}`
    );
  },
};
</script>

<style lang="scss" scoped></style>
