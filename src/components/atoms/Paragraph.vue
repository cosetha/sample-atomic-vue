<template>
  <p :class="align">
    <slot>{{content}}</slot>
  </p>
</template>

<script>
export default {
  name: "Paragraph",
  data() {
    return {};
  },
  props: {
    content: String,
    align: {
      type: String,
      default: "center"
    }
  }
};
</script>

<style scoped lang="postcss">
.left {
  @apply text-left;
}
.center {
  @apply text-center;
}
.right {
  @apply text-right;
}
</style>
