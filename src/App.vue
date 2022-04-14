<template>
  <the-validation name="validation-1">
    <the-article>
      <div>
        <the-validation name="validation-2"> </the-validation>
      </div>
    </the-article>
    <the-article>
      <the-validation name="validation-3">
        <the-validation name="validation-4"></the-validation>
        <the-validation name="validation-5"></the-validation>
        <the-article>
          <the-validation name="validation-6">
            <the-validation name="validation-7"></the-validation>
            <the-validation name="validation-8"></the-validation>
          </the-validation>
        </the-article>
      </the-validation>
    </the-article>
    <the-validation name="validation-9"></the-validation>
  </the-validation>
</template>

<script>
import TheValidation from "@/components/TheValidation.vue";
import TheArticle from "@/components/TheArticle.vue";
export default {
  name: "App",
  components: {
    TheValidation,
    TheArticle,
  },
};
</script>
