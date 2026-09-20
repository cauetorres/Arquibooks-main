<script setup>
import { ref } from 'vue'

const email = ref('')
const senha = ref('')

function entrar() {
  console.log('Login:', email.value, senha.value)
  // aqui depois entra a lógica real de autenticação
}
</script>

<template>
  <div class="login-container">
    <form @submit.prevent="entrar" class="login-form">
      <h2 class="mb-4 text-center">Login</h2>

      <div class="mb-3">
        <label class="form-label">E-mail</label>
        <input v-model="email" type="email" class="form-control" required />
      </div>

      <div class="mb-3">
        <label class="form-label">Senha</label>
        <input v-model="senha" type="password" class="form-control" required />
      </div>

      <button type="submit" class="btn btn-primary w-100">Entrar</button>
    </form>
  </div>
</template>

<style scoped>
.login-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

.login-form {
  width: 100%;
  max-width: 360px;
  padding: 2rem;
  border: 1px solid #ddd;
  border-radius: 8px;
}
</style>