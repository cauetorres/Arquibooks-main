<script setup>
defineProps({
  pageTitle: { type: String, required: true },
  active: { type: String, required: true },
})
</script>

<template>
  <div class="app-layout">
    <aside class="sidebar">
      <div class="sidebar-logo">
        <img src="/src/assets/logo_arquibooks.jpeg" alt="ArquiBooks" widht="90" height="90" class="logo-icon-img" />
        <div>
          <h1>ArquiBooks</h1>
          <small>SISTEMA DE GESTÃO DE BIBLIOTECA</small>
        </div>
      </div>

      <nav class="sidebar-nav">
        <div class="nav-group">
          <p class="nav-group-title">Principal</p>
          <RouterLink to="/dashboard" class="nav-link" :class="{ active: active === 'dashboard' }">
            <span class="nav-icon">📊</span> Dashboard
          </RouterLink>
        </div>

        <div class="nav-group">
          <p class="nav-group-title">Acervo</p>
          <RouterLink to="/livros" class="nav-link" :class="{ active: active === 'livros' }">
            <span class="nav-icon">📖</span> Livros
          </RouterLink>
          <RouterLink to="/alunos" class="nav-link" :class="{ active: active === 'alunos' }">
            <span class="nav-icon">👥</span> Alunos
          </RouterLink>
        </div>

        <div class="nav-group">
          <p class="nav-group-title">Circulação</p>
          <RouterLink to="/emprestimos" class="nav-link" :class="{ active: active === 'emprestimos' }">
            <span class="nav-icon">⬇️</span> Empréstimos
          </RouterLink>
          <RouterLink to="/devolucoes" class="nav-link" :class="{ active: active === 'devolucoes' }">
            <span class="nav-icon">⬆️</span> Devoluções
          </RouterLink>
        </div>

        <div class="nav-group">
          <p class="nav-group-title">Comunicação</p>
          <RouterLink to="/email" class="nav-link" :class="{ active: active === 'email' }">
            <span class="nav-icon">✉️</span> E-mails Automáticos
          </RouterLink>
        </div>
      </nav>

      <div class="sidebar-user">
        <div class="user-avatar"></div>
        <div>
          <strong>Bibliotecária</strong>
          <small>Administrador</small>
        </div>
      </div>
    </aside>

    <div class="main-area">
      <header class="topbar">
        <h2>{{ pageTitle }}</h2>
        <div class="topbar-actions">
          <input type="text" class="topbar-search" placeholder="" />
          <button class="icon-round-btn">🔔</button>
        </div>
      </header>

      <main class="page-content">
        <slot />
      </main>
    </div>
  </div>
</template>