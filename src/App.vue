import { RouterLink, RouterView } from 'vue-router'
<template>
  <BottomTabNavigation />
  <RouterView />
</template>

<script>
import BottomTabNavigation from './views/BottomTabNavigation.vue'
export default {
  components: {
    BottomTabNavigation
  },
  methods: {
    isActive(path) {
      return this.$route.path === path;
    }
  },
};
</script>

