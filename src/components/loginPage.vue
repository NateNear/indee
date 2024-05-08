<template>
  <div class="grid">
    <div class="bg-black rounded-t-lg p-8 backdrop-filter backdrop-blur-[10px] bg-opacity-80">
      <div class="flex items-center justify-center mb-6">
        <img :src="mgmLogo" alt="MGM Global Distribution" class="h-12 filter invert mr-4" />
        <span class="text-xl text-white">Global<br />Distribution</span>
      </div>
      <div class="mx-6">
        <h1 class="text-white text-xl font-semibold mb-4 text-left">Sign in</h1>
        <form @submit.prevent="handleSubmit">
          <div class="mb-4">
            <p class="text-[#1A68FF] font-medium">Email:</p>
            <input
              v-model="email"
              type="email"
              placeholder="Enter your email address"
              class="w-80 px-3 py-2 rounded-sm bg-zinc-900 text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500"
              required
            />
          </div>
          <div class="mb-4">
            <p class="text-[#1A68FF] font-medium">Password:</p>
            <input
              v-model="password"
              type="password"
              placeholder="Enter your password"
              class="w-full px-3 py-2 rounded-sm bg-zinc-900 text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500"
              required
            />
            <a href="#" class="text-[#BCBCBC] text-sm mt-2 block text-right">Forgot Password?</a>
          </div>
          <div class="flex items-center mb-6">
            <input v-model="rememberMe" type="checkbox" class="mr-2 w-4 h-4" id="rememberMe" />
            <label for="rememberMe" class="text-white text-[15px]">Keep me signed in for 30 days</label>
          </div>
          <button
            type="submit"
            class="w-full py-2 rounded-md bg-[#0057FF] text-white font-bold hover:bg-blue-600 transition-colors duration-300 mx-auto"
          >
            SIGN IN
          </button>
        </form>
        <p class="text-white text-start mt-4 text-[15px]">
          Read our Terms of Service
        </p>
      </div>
    </div>

    <!-- New div for "OTHER WAYS TO WATCH" -->
    <div class="bg-[#24272C] p-4">
      <p class="text-[#D5D5D5] text-[8px] text-center">OTHER WAYS TO WATCH</p>
      <div class="flex items-center justify-center my-4">
        <img :src="appletvLogo" alt="Apple TV" class="h-5 mr-4 filter invert" />
        <img :src="iosLogo" alt="iOS" class="h-5 mr-4 filter invert" />
        <img :src="rokuLogo" alt="Roku" class="h-5 mr-4 filter invert" />
        <img :src="amazonFireLogo" alt="Amazon Fire" class="h-5 filter invert" />
      </div>
      <p class="text-[#D5D5D5] text-[8px] text-center">Search for AppleTV+ FYC on your App Store</p>
    </div>
  </div>
</template>

<script>
import mgmLogo from '../assets/mgm.png';
import appletvLogo from '../assets/logos/appletv.png';
import iosLogo from '../assets/logos/ios.png';
import rokuLogo from '../assets/logos/roku.png';
import amazonFireLogo from '../assets/logos/firetv.svg';

export default {
  name: 'LoginPage',
  data() {
    return {
      email: '',
      password: '',
      rememberMe: false,
      mgmLogo,
      appletvLogo,
      iosLogo,
      rokuLogo,
      amazonFireLogo,
    };
  },
  methods: {
    handleSubmit() {
      console.log('Email:', this.email);
      console.log('Password:', this.password);
      console.log('Remember Me:', this.rememberMe);
    },
  },
};
</script>
