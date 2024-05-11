<template>
  <div class="min-h-screen relative">
    <div v-if="isMobile" class="absolute inset-0 flex items-center justify-center">
      <div class="w-full">
        <LoginPage />
      </div>
    </div>
    <div>
      <div
        class="absolute inset-0 bg-cover"
        :style="{ 'background-image': `url(${backgroundImage})` }"
      ></div>
      <div class="absolute inset-0 bg-black bg-opacity-50 backdrop-blur-sm"></div>
      <div class="absolute inset-0 flex items-center justify-center">
        <div class="w-full sm:w-96">
          <LoginPage />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import LoginPage from './components/loginPage.vue'
import backgroundImage from './assets/netflix_bg.jpg'

export default {
  name: 'App',
  components: {
    LoginPage
  },
  data() {
    return {
      backgroundImage,
      isMobile: false
    }
  },
  mounted() {
    this.isMobile = window.innerWidth <= 768

    window.addEventListener('resize', this.updateIsMobile)
  },
  methods: {
    updateIsMobile() {
      this.isMobile = window.innerWidth <= 768
    }
  },
  beforeUnmount() {
    window.removeEventListener('resize', this.updateIsMobile)
  }
}
</script>
