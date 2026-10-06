<script setup>
import { ref } from 'vue'
import LoginPage from './components/LoginPage.vue'
import Dashboard from './components/Dashboard.vue'

const username = ref('')

function handleLogin(name) {
  username.value = name
}

function handleLogout() {
  username.value = ''
}
</script>

<template>
  <Dashboard v-if="username" :username="username" @logout="handleLogout" />
  <LoginPage v-else @login="handleLogin" />
</template>
