<template>
  <a
    v-if="href"
    :href="href"
    :target="target"
    class="sba-nav-item"
    r
    rel="noopener noreferrer"
  >
    <slot />
  </a>
  <router-link v-else-if="to" :to="to" class="sba-nav-item">
    <slot />
  </router-link>

  <div v-else class="sba-nav-item">
    <slot />
  </div>
</template>

<script lang="ts" setup>
defineProps({
  href: {
    type: String,
    default: null,
  },
  target: {
    type: String,
    default: '_blank',
  },
  to: {
    type: String,
    default: null,
  },
});
</script>

<style scoped>
.sba-nav-item {
  @apply px-3 py-2 rounded lg:self-center hover:bg-sba-700;
}
</style>
<style>
.sba-nav-item.is-active {
  @apply bg-sba-700;
}
</style>
