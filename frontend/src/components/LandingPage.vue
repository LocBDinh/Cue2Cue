<template>
  <div class="h-screen overflow-y-scroll snap-y snap-mandatory">
    <!-- Landing Page - Hero -->
    <section class="h-screen snap-start relative flex flex-col bg-[#E86A54]">
      <!-- Navigation -->
      <nav class="flex justify-between items-center px-8 py-6 md:px-12 md:py-8">
        <div class="flex items-center gap-1">
          <span class="text-[#F5C26D] tracking-wider uppercase" style="font-size: 1.5rem; font-weight: 700">
            CUE
          </span>
          <span class="text-white" style="font-size: 1.5rem; font-weight: 700">
            2
          </span>
          <span class="text-[#F5C26D] tracking-wider uppercase" style="font-size: 1.5rem; font-weight: 700">
            CUE
          </span>
        </div>
        <div class="flex gap-8">
           <a href="#features" class="relative text-white uppercase tracking-wider group transition-all duration-300"
              style="font-size: 0.875rem; font-weight: 600; letter-spacing: 0.1em">
              FEATURES
              <span
                class="absolute left-0 top-1/2 w-0 h-[2px] bg-white group-hover:w-full transition-all duration-300"></span>
            </a>
            <a href="#contact" class="relative text-white uppercase tracking-wider group transition-all duration-300"
              style="font-size: 0.875rem; font-weight: 600; letter-spacing: 0.1em">
              CONTACT
              <span
                class="absolute left-0 top-1/2 w-0 h-[2px] bg-white group-hover:w-full transition-all duration-300"></span>
            </a>
        </div>
      </nav>

      <!-- Hero Content -->
      <div class="flex-1 flex items-center justify-center px-8 md:px-16">
        <h1 class="text-center text-white uppercase tracking-tight"
          style="font-size: clamp(2.5rem, 8vw, 6rem); font-weight: 800; line-height: 1.1">
          KEEP YOUR
          <br />
          DANCERS
          <br />
          ON TIME
        </h1>
      </div>

      <!-- Bottom Badge -->
      <div class="absolute bottom-8 left-8 md:bottom-12 md:left-12">
        <div
          class="bg-white rounded-full w-24 h-24 md:w-28 md:h-28 flex items-center justify-center rotate-[-15deg] shadow-lg">
          <span class="text-[#E86A54] uppercase tracking-wide text-center"
            style="font-size: 0.65rem; font-weight: 700; line-height: 1.2">
            5, 6, 7, 8!
          </span>
        </div>
      </div>

      <!-- Moving Scroll Indicator -->
      <div class="absolute bottom-8 right-8 md:bottom-12 md:right-12 animate-bounce">
        <div class="text-white opacity-70">
          <svg width="30" height="30" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"
            stroke-linecap="round" stroke-linejoin="round">
            <path d="M12 5v14M19 12l-7 7-7-7" />
          </svg>
        </div>
      </div>
    </section>

    <!-- Sign In/Sign Up Section -->
    <section class="h-screen snap-start relative flex items-center justify-center">
      <!-- Background Image -->
      <div class="absolute inset-0">
        <img src="/scrolledLanding.jpg""
          alt=" Clock Image Background" class="w-full h-full object-cover" />
        <!-- Overlay -->
        <div class="absolute inset-0 bg-black/40"></div>
      </div>

      <!-- Content -->
      <div class="relative z-10 text-center px-8 max-w-4xl mx-auto">
        <h2 class="text-white mb-8"
          style="font-size: clamp(2rem, 6vw, 4.5rem); font-weight: 800; line-height: 1.1; letter-spacing: -0.02em">
          READY TO GET STARTED?
        </h2>
        <p class="text-white/90 mb-12 max-w-2xl mx-auto" style="font-size: clamp(1rem, 2vw, 1.5rem); line-height: 1.6">
          Send rehearsal reminders, schedule changes, and
          hell week updates to your dancers instantly!
        </p>
        <div class="flex flex-wrap gap-4 justify-center">
          <button @click="handleOpenAuth('signin')"
            class="cursor-pointer bg-white hover:bg-gray-100 text-[#E86A54] px-12 py-6 shadow-xl hover:shadow-2xl hover:scale-105 transition-all"
            style="font-size: 1.125rem; font-weight: 700; border-radius: 9999px">
            Sign In
          </button>
          <button @click="handleOpenAuth('signup')"
            class="cursor-pointer bg-[#E86A54] hover:bg-[#D45744] text-white px-12 py-6 shadow-xl hover:shadow-2xl hover:scale-105 transition-all"
            style="font-size: 1.125rem; font-weight: 700; border-radius: 9999px">
            Sign Up
          </button>
        </div>
      </div>

      <!-- Navigation at top -->
      <nav class="absolute top-0 left-0 right-0 flex justify-between items-center px-8 py-6 md:px-12 md:py-8">
        <div class="flex items-center gap-1">
          <span class="text-[#F5C26D] tracking-wider uppercase" style="font-size: 1.5rem; font-weight: 700">
            CUE
          </span>
          <span class="text-white" style="font-size: 1.5rem; font-weight: 700">
            2
          </span>
          <span class="text-[#F5C26D] tracking-wider uppercase" style="font-size: 1.5rem; font-weight: 700">
            CUE
          </span>
        </div>
        <div class="flex gap-8">
          <div class="flex gap-8">
            <a href="#features" class="relative text-white uppercase tracking-wider group transition-all duration-300"
              style="font-size: 0.875rem; font-weight: 600; letter-spacing: 0.1em">
              FEATURES
              <span
                class="absolute left-0 top-1/2 w-0 h-[2px] bg-white group-hover:w-full transition-all duration-300"></span>
            </a>
            <a href="#contact" class="relative text-white uppercase tracking-wider group transition-all duration-300"
              style="font-size: 0.875rem; font-weight: 600; letter-spacing: 0.1em">
              CONTACT
              <span
                class="absolute left-0 top-1/2 w-0 h-[2px] bg-white group-hover:w-full transition-all duration-300"></span>
            </a>
          </div>
        </div>
      </nav>
    </section>

    <!-- Auth Modal -->
    <AuthModal v-if="showAuthModal" :is-open="showAuthModal" :initial-mode="authMode" @close="showAuthModal = false"
      @sign-in="handleSignIn" />
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import AuthModal from './AuthModal.vue'

// Define emits
const emit = defineEmits<{
  signIn: [userData: { name: string; email: string }]
}>()

// State
const showAuthModal = ref(false)
const authMode = ref<'signin' | 'signup'>('signin')

// Methods
const handleOpenAuth = (mode: 'signin' | 'signup') => {
  authMode.value = mode
  showAuthModal.value = true
}

const handleSignIn = (userData: { name: string; email: string }) => {
  emit('signIn', userData)
}
</script>

<style scoped>
/* All styling is handled by Tailwind CSS utility classes */
</style>
