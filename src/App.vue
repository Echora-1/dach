<template>
  <DefaultLayout>
    <router-view />
  </DefaultLayout>
</template>

<script>
import DefaultLayout from "@/components/layouts/DefaultLayout";
export default {
  name: "App",
  components: { DefaultLayout },
};
</script>

<style lang="scss">
@import "./assets/styles/normalize.css";
@import "./assets/styles/global.scss";

:root {
  --primary: #1fb537;
}
</style>
