<template>
  <component :is="tagName" :class="currentClass">
    <slot v-if="noBody" />
    <template v-else>
      <div v-if="hasHeaderSlot" ref="header" :class="headerClass">
        <slot name="header" />
      </div>
      <div v-else-if="header" ref="header" :class="headerClass" v-text="header" />
      <div ref="body" :class="bodyClass">
        <slot />
      </div>
      <div v-if="hasFooterSlot" ref="footer" :class="footerClass">
        <slot name="footer" />
      </div>
    </template>
  </component>
</template>

<script>
const TCard = {
  baseClass: "bg-white rounded border",
  headerClass: "px-6 py-3 text-xl border-b",
  bodyClass: "p-6",
  footerClass: "px-6 py-3 border-t"
};

export default {
  name: "Card",

  props: {
    tagName: {
      type: String,
      default: "div"
    },
    header: {
      type: String,
      default: null
    },
    noBody: {
      type: Boolean,
      default: false
    },
    baseClass: {
      type: [String, Object, Array],
      default: TCard.baseClass
    },
    bodyClass: {
      type: [String, Object, Array],
      default: TCard.bodyClass
    },
    headerClass: {
      type: [String, Object, Array],
      default: TCard.headerClass
    },
    footerClass: {
      type: [String, Object, Array],
      default: TCard.footerClass
    }
  },

  computed: {
    hasHeaderSlot() {
      return !!this.$slots["header"];
    },
    hasFooterSlot() {
      return !!this.$slots["footer"];
    },

    currentClass() {
      let classes = [`${this.$options._componentTag}`];

      if (this.baseClass) {
        classes.push(this.baseClass);
      }

      return classes;
    }
  }
};
</script>
