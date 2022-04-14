<template>
  <div class="article">
    <h3>Article</h3>
    <slot />
  </div>
</template>

<script>
export default {
  name: "TheArticle",
};
</script>

<style scoped>
.article {
  padding: 1rem;
}
</style>
