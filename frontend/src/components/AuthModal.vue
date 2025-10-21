<template>
  <div
    v-if="isOpen"
    class="fixed inset-0 z-50 flex items-center justify-center"
    @click.self="handleClose"
  >
    <!-- Backdrop -->
    <div class="absolute inset-0 bg-black/50"></div>
    
    <!-- Modal Content -->
    <div class="relative bg-white rounded-lg shadow-xl max-w-md w-full mx-4 max-h-[90vh] overflow-y-auto">
      <!-- Header -->
      <div class="p-6 border-b">
        <h2>{{ isSignUp ? 'Create Account' : 'Sign In' }}</h2>
        <button
          @click="handleClose"
          class="absolute top-6 right-6 text-muted-foreground hover:text-foreground"
          aria-label="Close"
        >
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M15 5L5 15M5 5l10 10" />
          </svg>
        </button>
      </div>

      <!-- Body -->
      <div class="p-6 space-y-4">
        <!-- Social Auth Buttons -->
        <div class="space-y-3">
          <button
            @click="handleGoogleSignIn"
            class="w-full flex items-center justify-center gap-2 px-4 py-2 border rounded-lg hover:bg-gray-50 transition-colors"
          >
            <svg class="w-5 h-5" viewBox="0 0 24 24">
              <path fill="#4285F4" d="M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92c-.26 1.37-1.04 2.53-2.21 3.31v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.09z"/>
              <path fill="#34A853" d="M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z"/>
              <path fill="#FBBC05" d="M5.84 14.09c-.22-.66-.35-1.36-.35-2.09s.13-1.43.35-2.09V7.07H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.93l2.85-2.22.81-.62z"/>
              <path fill="#EA4335" d="M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.07l3.66 2.84c.87-2.6 3.3-4.53 6.16-4.53z"/>
            </svg>
            Continue with Google
          </button>
        </div>

        <div class="relative">
          <div class="absolute inset-0 flex items-center">
            <span class="w-full border-t"></span>
          </div>
          <div class="relative flex justify-center">
            <span class="bg-white px-2 text-muted-foreground">
              Or continue with email
            </span>
          </div>
        </div>

        <!-- Email Sign In Form -->
        <form @submit.prevent="handleEmailSignIn" class="space-y-4">
          <div v-if="isSignUp" class="space-y-2">
            <label for="name" class="block">Name</label>
            <input
              id="name"
              v-model="name"
              type="text"
              placeholder="Enter your name"
              class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-[#E86A54]"
            />
          </div>
          
          <div class="space-y-2">
            <label for="email" class="block">Email</label>
            <input
              id="email"
              v-model="email"
              type="email"
              placeholder="Enter your email"
              required
              class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-[#E86A54]"
            />
          </div>
          
          <div class="space-y-2">
            <label for="password" class="block">Password</label>
            <input
              id="password"
              v-model="password"
              type="password"
              placeholder="Enter your password"
              required
              class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-[#E86A54]"
            />
          </div>

          <button
            type="submit"
            class="w-full bg-[#E86A54] hover:bg-[#D45744] text-white px-4 py-2 rounded-lg transition-colors"
          >
            {{ isSignUp ? 'Sign Up' : 'Sign In' }}
          </button>
        </form>

        <div class="text-center">
          <button
            type="button"
            @click="isSignUp = !isSignUp"
            class="text-muted-foreground hover:text-foreground transition-colors underline"
          >
            {{ isSignUp ? 'Already have an account? Sign in' : "Don't have an account? Sign up" }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, watch } from 'vue'

interface Props {
  isOpen: boolean
  initialMode?: 'signin' | 'signup'
}

const props = withDefaults(defineProps<Props>(), {
  initialMode: 'signin'
})

const emit = defineEmits<{
  close: []
  signIn: [userData: { name: string; email: string }]
}>()

const isSignUp = ref(props.initialMode === 'signup')
const name = ref('')
const email = ref('')
const password = ref('')

watch(() => props.initialMode, (newMode) => {
  isSignUp.value = newMode === 'signup'
})

const handleClose = () => {
  emit('close')
}

const handleGoogleSignIn = () => {
  emit('signIn', {
    name: 'Google User',
    email: 'user@gmail.com'
  })
  handleClose()
}

const handleEmailSignIn = () => {
  emit('signIn', {
    name: name.value || email.value.split('@')[0] || '',
    email: email.value
  })
  handleClose()
}
</script>

<style scoped>
/* All styling is handled by Tailwind CSS utility classes */
</style>
