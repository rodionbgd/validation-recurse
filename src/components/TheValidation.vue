<template>
  <div class="nav-item">
    <span class="nav-link-text" @click="validate">{{ name }}</span>
    <div class="nav-item-inner" v-if="hasChildren" ref="child">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "TheValidation",
  props: {
    name: {
      type: String,
      default: "",
    },
  },
  computed: {
    hasChildren() {
      if (this.$slots.default) {
        return !!this.$slots.default;
      }
      return false;
    },
  },
  methods: {
    validate() {
      console.log(this.name);
      this.$slots.default?.forEach((component) => {
        if (component.componentInstance.$options.name !== this.$options.name) {
          component.componentInstance.$children.forEach((c) => {
            if (c?.$options?.name === this.$options.name) {
              c.validate();
            }
          });
        }
        if (
          component.componentInstance?.$options?.name === this.$options.name
        ) {
          component.componentInstance.validate();
        }
      });
    },
  },
};
</script>

<style scoped>
.nav-item {
  padding-left: 1rem;
}
</style>
