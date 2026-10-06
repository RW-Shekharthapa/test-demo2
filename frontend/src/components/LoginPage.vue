<script setup>
import { ref } from 'vue'

const emit = defineEmits(['login'])

const username = ref('')
const password = ref('')
const error = ref('')

function handleSubmit() {
  if (username.value !== 'admin' || password.value !== '12345678') {
    error.value = 'Invalid username or password.'
    return
  }
  error.value = ''
  emit('login', username.value)
}
</script>

<template>
  <div class="login-page">
    <form class="login-card" @submit.prevent="handleSubmit">
      <h1>Sign in</h1>
      <label for="username">Username</label>
      <input id="username" v-model="username" type="text" autocomplete="username" />
      <label for="password">Password</label>
      <input id="password" v-model="password" type="password" autocomplete="current-password" />
      <p v-if="error" class="error">{{ error }}</p>
      <button type="submit">Log in</button>
    </form>
  </div>
</template>

<style scoped>
.login-page {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}
.login-card {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
  width: 320px;
  padding: 2rem;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
}
.login-card h1 {
  margin: 0 0 0.5rem;
  font-size: 1.5rem;
  text-align: center;
}
input {
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 1rem;
}
button {
  padding: 0.6rem;
  border: none;
  border-radius: 4px;
  background: #42b883;
  color: white;
  font-size: 1rem;
  cursor: pointer;
}
.error {
  color: #d33;
  margin: 0;
  font-size: 0.9rem;
}
</style>
