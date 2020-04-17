<template>
  <div>
    <ul class="flex border-b">
      <li class="mr-1" v-for="link in links" :key="link.label">
        <Link :label="link.label" :path="link.path" type="dark" />
      </li>
    </ul>
  </div>
</template>

<script>
import Link from "../atoms/Link";

export default {
  name: "LinkList",
  components: {
    Link
  },
  data() {
    return {};
  },
  props: {
    links: Array,
    type: {
      type: String,
      default: null,
      validator: function(value) {
        return value === null || ["dark", "light"].indexOf(value) !== -1;
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
