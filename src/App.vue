<template>
  <div class="flex flex-col min-h-screen font-Roboto bg-weather-primary">
    <SideNavigation />
    <RouterView />
  </div>
  <Home />
</template>

<script>
import { RouterView } from "vue-router";
import SideNavigation from "./components/SideNavigation.vue";
export default {
  components: { SideNavigation },
};
</script>

<style></style>
