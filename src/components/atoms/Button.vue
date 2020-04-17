<template>
  <button :class="currentClass" :variant="variant" :size="size">
    <slot>{{label}}</slot>
  </button>
</template>

<script>
const TButton = {
  baseClass: "border block rounded inline-flex items-center justify-center",
  defaultClass:
    "bg-white border-gray-400 hover:bg-gray-100 hover:border-gray-500",
  primaryClass:
    "text-white bg-blue-500 border-blue-500 hover:bg-blue-600 hover:border-blue-600",
  secondaryClass:
    "border-blue-500 text-blue-500 bg-white hover:border-blue-600 hover:text-blue-600 hover:bg-white",
  tertiaryClass:
    "border block underline text-blue-500 border-transparent bg-transparent hover:text-blue-600",
  successClass:
    "text-white bg-green-500 border-green-500 hover:bg-green-600 hover:border-green-600",
  dangerClass:
    "text-white bg-red-500 border-red-500 hover:bg-red-600 hover:border-red-600",
  warningClass:
    "text-yellow-900 bg-yellow-500 border-yellow-500 hover:bg-yellow-600 hover:border-yellow-600",
  disabledClass: "cursor-not-allowed opacity-75",
  defaultSizeClass: "px-6 py-3",
  largeSizeClass: "px-8 py-4 text-lg",
  smallSizeClass: "px-4 py-2 text-sm"
};
export default {
  name: "Button",
  props: {
    label: String,
    size: {
      type: String,
      default: null,
      validator: function(value) {
        return value === null || ["lg", "sm"].indexOf(value) !== -1;
      }
    },
    variant: {
      type: String,
      default: null,
      validator: function(value) {
        return (
          value === null ||
          [
            "primary",
            "secondary",
            "tertiary",
            "danger",
            "warning",
            "success"
          ].indexOf(value) !== -1
        );
      }
    }
  },
  computed: {
    currentClass() {
      let classes = [
        `${this.$options._componentTag}`,
        `${this.$options._componentTag}-size-${this.size || "default"}`,
        TButton.baseClass
      ];

      if (this.size === null) {
        classes.push(TButton.defaultSizeClass);
      } else if (this.size === "sm") {
        classes.push(TButton.smallSizeClass);
      } else if (this.size === "lg") {
        classes.push(TButton.largeSizeClass);
      }

      switch (this.variant) {
        case "primary":
          classes.push(TButton.primaryClass);
          break;
        case "secondary":
          classes.push(TButton.secondaryClass);
          break;
        case "tertiary":
          classes.push(TButton.tertiaryClass);
          break;
        case "danger":
          classes.push(TButton.dangerClass);
          break;
        case "warning":
          classes.push(TButton.warningClass);
          break;
        case "success":
          classes.push(TButton.successClass);
          break;
        default:
          classes.push(TButton.defaultClass);
          break;
      }

      return classes;
    }
  }
};
</script>

<style scoped lang="postcss">
</style>