<script setup>
defineProps(['username'])
defineEmits(['logout'])
</script>

<template>
  <div class="dashboard">
    <header>
      <h1>Dashboard</h1>
      <button @click="$emit('logout')">Log out</button>
    </header>
    <p>Welcome, {{ username }}!</p>
  </div>
</template>

<style scoped>
.dashboard {
  max-width: 600px;
  margin: 2rem auto;
  padding: 1rem;
}
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
button {
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 4px;
  background: #e0e0e0;
  cursor: pointer;
}
</style>
