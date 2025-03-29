<template>
  <div>
    <v-app-bar>
      <div class="menu-container">
        <div class="d-flex justify-space-between align-center w-100">
          <div>
            <v-img :src="logo" height="100" width="40"></v-img>
          </div>

          <div class="d-flex align-center gap-4">
            <p class="mr-6">Home</p>

            <!-- Our Services with Dropdown -->
            <v-menu open-on-hover class="px-6">
              <template v-slot:activator="{ props }" class="mx-6">
                <div v-bind="props" class="services">Our Services</div>
              </template>

              <v-list>
                <v-list-item
                  v-for="(item, index) in services"
                  :key="index"
                  @click="navigateTo(item.route)"
                >
                  <v-list-item-title class="px-0"
                    >{{ item.title }}
                  </v-list-item-title>
                </v-list-item>
              </v-list>
            </v-menu>

            <p class="ml-6">Gallery</p>
            <p class="ml-6">Contact us</p>
            <v-divider class="mx-6" vertical></v-divider>
            <div class="d-flex flex-column">
              <p>Get in touch</p>
              <p>Call us</p>
            </div>
          </div>
        </div>
      </div>
    </v-app-bar>
  </div>
</template>

<script setup>
import { useRouter } from "vue-router";
import logo from "@/assets/logo.png";

const router = useRouter();
const services = [
  { title: "Service 1", route: "/solar-installation" },
  { title: "Service 2", route: "/energy-audit" },
  { title: "Service 3", route: "/battery-storage" },
];

const navigateTo = (route) => {
  router.push(route);
};
</script>

<style scoped>
.menu-container {
  max-width: 1140px;
  margin: 0 auto;
  padding: 0;
  width: 100%;
}

.services {
  cursor: pointer;
  color: black;
  transition: color 0.3s ease-in-out;
}

.services:hover {
  color: red;
}

.v-list {
  padding: 0 5px !important;
  margin: 10px 0 !important;
}
.v-list-item {
  padding: 4px 12px !important; /* Adjust as needed */
  justify-content: flex-start !important; /* Align text to the left */
  border-bottom: 1px solid rgba(0, 0, 0, 0.12);
}
</style>
