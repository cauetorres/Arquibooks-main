<script setup>
import Sidebar from '../components/Sidebar.vue'

const emprestimos = [
  { rm: '10705', aluno: 'Lucas Ferreira Costa', livro: 'Dom Casmurro', emprestimo: '09/06/2026', previsao: '23/06/2026', status: 'Emprestado', badge: 'badge-emprestado' },
  { rm: '10710', aluno: 'Mariana Costa Santos', livro: '1984', emprestimo: '08/06/2026', previsao: '22/06/2026', status: 'Vencendo', badge: 'badge-vencendo' },
  { rm: '10715', aluno: 'Beatriz Oliveira Almeida', livro: 'A Hora da Estrela', emprestimo: '06/06/2026', previsao: '20/06/2026', status: 'Emprestado', badge: 'badge-emprestado' },
  { rm: '10720', aluno: 'Gabriel Santos Oliveira', livro: 'Iracema', emprestimo: '02/06/2026', previsao: '16/06/2026', status: 'Atrasado', badge: 'badge-atrasado' },
  { rm: '10725', aluno: 'Rafael Almeida Martins', livro: 'O Alquimista', emprestimo: '28/05/2026', previsao: '11/06/2026', status: 'Emprestado', badge: 'badge-emprestado' },
]
</script>

<template>
  <Sidebar page-title="Empréstimos" active="emprestimos">
    <div class="page-header">
      <h1>Empréstimos</h1>
      <button class="btn-primary-action">Novo Empréstimo</button>
    </div>

    <div class="filter-bar">
      <input type="text" placeholder="Pesquisar por aluno, livro ou RM..." />
      <select><option>Todos os status</option></select>
    </div>

    <div class="table-card">
      <table class="data-table">
        <thead>
          <tr>
            <th>RM</th>
            <th>Aluno</th>
            <th>Livro</th>
            <th>Empréstimo</th>
            <th>Previsão de Devolução</th>
            <th>Status</th>
            <th>Ação</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(e, i) in emprestimos" :key="i">
            <td>{{ e.rm }}</td>
            <td>{{ e.aluno }}</td>
            <td>{{ e.livro }}</td>
            <td>{{ e.emprestimo }}</td>
            <td>{{ e.previsao }}</td>
            <td><span class="badge" :class="e.badge">{{ e.status }}</span></td>
            <td>
              <button class="action-btn check">✓</button>
              <button class="action-btn renew">⟳</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </Sidebar>
</template>