<template>
  <v-app>
    <Layout>
      <v-main>
        <router-view />
      </v-main>
    </Layout>
  </v-app>
</template>

<script setup>
import Layout from "@/components/layout/index.vue";
</script>
