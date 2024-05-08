<template>
  <div class="min-h-screen relative">
    <div class="absolute inset-0 bg-cover" :style="{ 'background-image': `url(${backgroundImage})` }"></div>
    <div class="absolute inset-0 bg-black bg-opacity-50 backdrop-blur-sm"></div>
    <div class="absolute inset-0 flex items-center justify-center">
      <LoginPage />
    </div>
  </div>
</template>

<script>
import LoginPage from './components/loginPage.vue';
import backgroundImage from './assets/netflix_bg.jpg';

export default {
  name: 'App',
  components: {
    LoginPage,
  },
  data() {
    return {
      backgroundImage,
    };
  },
};
</script>

<style scoped>
/* Add any additional styling if needed */
</style>
