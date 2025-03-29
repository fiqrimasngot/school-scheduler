<template>
  <v-app>
    <div class="layout-container">
      <Menu />
      <slot />
    </div>
  </v-app>
</template>
_

<script setup>
import Menu from "@/components/layout/menu/index.vue";
</script>

<style scoped>
.layout-container {
  max-width: 1140px; /* Set your preferred max width */
  margin: 0 auto; /* Center the content */
  padding: 0 16px; /* Add some padding for responsiveness */
  width: 100%;
}
</style>
