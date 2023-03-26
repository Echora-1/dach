<template>
  <div class="layout">
    <BaseHeader />
    <main class="layout__main">
      <slot />
    </main>
    <BaseFooter />
  </div>
</template>

<script>
import BaseHeader from "@/components/base/BaseHeader";
import BaseFooter from "@/components/base/BaseFooter";
export default {
  components: { BaseFooter, BaseHeader },
};
</script>

<style lang="scss" scoped>
.layout {
  overflow: hidden;
}
</style>
