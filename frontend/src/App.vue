<template>
  <Landing v-if="!isAuthenticated" @sign-in="handleSignIn" />
  <Dashboard v-else :user="user!" @sign-out="handleSignOut" />
</template>

<script setup lang="ts">
import { ref } from 'vue'
import Landing from './components/LandingPage.vue'

interface User {
  name: string
  email: string
}

const isAuthenticated = ref(false)
const user = ref<User | null>(null)

const handleSignIn = (userData: User) => {
  user.value = userData
  isAuthenticated.value = true
}

const handleSignOut = () => {
  user.value = null
  isAuthenticated.value = false
}
</script>

<style scoped>
/* All styling is handled by Tailwind CSS utility classes */
</style>
