<template>
  <router-link :class="currentClass" :type="type" :to="path" :isDisabled="isDisabled">
    {{ label }}
    <slot></slot>
  </router-link>
</template>

<script>
const TLink = {
  baseClass: "inline-block py-2 px-4",
  lightClass:
    " border-black border-b rounded-b inline-block py-2 px-4 text-black hover:text-gray-500 hover:border-gray-500 font-semibold",
  darkClass:
    " border-white border-b inline-block py-2 px-4 text-gray-300 hover:text-blue-600 hover:border-blue-600 font-semibold",
  disabledClass:
    " border-gray-400 border-b rounded-b text-gray-400 cursor-not-allowed hover:border-gray-500 font-semibold",
  defaultClass: "text-blue-500 hover:text-blue-800"
};
export default {
  name: "Link",
  data() {
    return {};
  },
  props: {
    label: String,
    path: String,
    isDisabled: {
      type: Boolean,
      default: false
    },
    type: {
      type: String,
      default: null,
      validator: function(value) {
        return value === null || ["dark", "light"].indexOf(value) !== -1;
      }
    }
  },
  computed: {
    currentClass() {
      let classes = [`${this.$options._componentTag}`, TLink.baseClass];

      switch (this.type) {
        case "light":
          classes.push(TLink.lightClass);
          break;
        case "dark":
          classes.push(TLink.darkClass);
          break;
        default:
          classes.push(TLink.defaultClass);
          break;
      }
      if (this.isDisabled != false) {
        classes.push(TLink.disabledClass);
      }
      return classes;
    }
  }
};
</script>

<style scoped lang="postcss">
</style>
