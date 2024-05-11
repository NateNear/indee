<template>
  <div class="grid">
    <header
      class="bg-black rounded-t-lg p-4 backdrop-filter backdrop-blur-[10px] bg-opacity-80"
      aria-label="Login Form"
    >
      <div class="flex items-center justify-center my-3">
        <img
          :src="mgmLogo"
          alt="MGM Global Distribution Logo"
          class="h-12 filter invert pt-1 mr-2"
        />
        <div class="text-md font-semibold grid mb-2 text-white" style="line-height: 1">
          <p>Global</p>
          <p>Distribution</p>
        </div>
      </div>

      <div class="mx-6">
        <h1 class="text-white text-xl font-semibold mb-3 text-left">Sign in</h1>
        <form @submit.prevent="handleSubmit">
          <div class="mb-4">
            <label for="email" class="text-[#1A68FF] font-medium">Email:</label>
            <input
              id="email"
              v-model="email"
              type="email"
              placeholder="Enter your email address"
              class="w-full px-3 py-2 rounded-sm bg-zinc-900 text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500"
              required
              aria-label="Email Input"
            />
          </div>
          <div class="mb-4">
            <label for="password" class="text-[#1A68FF] font-medium">Password:</label>
            <input
              id="password"
              v-model="password"
              type="password"
              placeholder="Enter your password"
              class="w-full px-3 py-2 rounded-sm bg-zinc-900 text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500"
              required
              aria-label="Password Input"
            />
            <a href="#" class="text-[#BCBCBC] text-sm mt-2 block text-right">Forgot Password?</a>
          </div>
          <div class="flex items-center mb-4">
            <input
              v-model="rememberMe"
              type="checkbox"
              class="mr-2 w-4 h-4"
              id="rememberMe"
              aria-label="Remember Me Checkbox"
            />
            <label for="rememberMe" class="text-white text-[12px]"
              >Keep me signed in for 30 days</label
            >
          </div>
          <button
            type="submit"
            class="w-full py-2 rounded-md bg-[#0057FF] text-white font-medium hover:bg-blue-600 transition-colors duration-300 mx-auto"
            aria-label="Sign In Button"
          >
            SIGN IN
          </button>
        </form>
      </div>
    </header>

    <div
      v-if="showModal"
      class="fixed inset-0 bg-black bg-opacity-50 flex justify-center items-center"
    >
      <div class="bg-white p-4 rounded-lg shadow-lg">
        <h2 class="text-lg">Success!</h2>
        <p>{{ loginSuccessMessage }}</p>
        <button
          @click="closeModal"
          class="mt-4 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
        >
          Close
        </button>
      </div>
    </div>

    <footer class="bg-[#24272C] rounded-b-lg">
      <div class="my-auto bg-[#2D3137] h-7"></div>
      <div class="p-2">
        <p class="text-[#D5D5D5] text-[8px] text-center">OTHER WAYS TO WATCH</p>
        <div class="flex items-center justify-center my-3">
          <img :src="appletvLogo" alt="Apple TV Logo" class="h-4 mr-7 filter invert" />
          <img :src="iosLogo" alt="iOS Logo" class="h-4 mr-7 filter invert" />
          <img :src="rokuLogo" alt="Roku Logo" class="h-4 mr-7 filter invert" />
          <img :src="amazonFireLogo" alt="Amazon Fire Logo" class="h-6 filter invert" />
        </div>
        <p class="text-[#D5D5D5] text-[8px] text-center">
          Search for AppleTV+ FYC on your App Store
        </p>
      </div>
    </footer>
  </div>
</template>

<script>
import mgmLogo from '../assets/mgm.png'
import appletvLogo from '../assets/logos/appletv.png'
import iosLogo from '../assets/logos/ios.png'
import rokuLogo from '../assets/logos/roku.png'
import amazonFireLogo from '../assets/logos/firetv.png'
import { CIcon } from '@coreui/icons-vue'
import { cilExternalLink } from '@coreui/icons'

export default {
  name: 'LoginPage',
  data() {
    return {
      email: '',
      password: '',
      rememberMe: false,
      showModal: false,
      loginSuccessMessage: 'Login successful! Welcome to MGM Global Distribution.',
      mgmLogo,
      appletvLogo,
      iosLogo,
      rokuLogo,
      amazonFireLogo,
      cilExternalLink
    }
  },
  methods: {
    handleSubmit() {
      this.showModal = true
    },
    closeModal() {
      this.showModal = false
    }
  },
  components: {
    CIcon
  }
}
</script>
