<template>
  <nav class="flex items-center justify-between flex-wrap bg-teal-500 p-6">
    <div class="flex items-center flex-shrink-0 text-white mr-6">
      <AppLogo />
    </div>
    <div class="block flex-grow lg:flex lg:items-center lg:w-auto">
      <LinkList :links="links" />
    </div>
    <div class="nav-bar-cell right">
      <AppLink
        label="Github"
        path="https://github.com/sakihet/vue-atomic-design-template"
        :isNewWindow="true"
      />
    </div>
  </nav>
</template>

<script>
import AppLink from "../atoms/Link";
import AppLogo from "../atoms/Logo";
import LinkList from "../molecules/LinkList";

export default {
  name: "NavBar",
  data() {
    return {
      links: [
        {
          path: "/",
          label: "Index"
        },
        {
          path: "/atoms",
          label: "Atoms"
        },
        {
          path: "/molecules",
          label: "Molecules"
        },
        {
          path: "/organisms",
          label: "Organisms"
        }
      ]
    };
  },
  components: {
    AppLink,
    AppLogo,
    LinkList
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.nav-bar {
  border-bottom: 1px solid #eee;
  display: flex;
}
.left {
  text-align: left;
  flex: 1;
}
.center {
  text-align: center;
  flex: 4;
}
.right {
  text-align: right;
  flex: 1;
}
</style>
