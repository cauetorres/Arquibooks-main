<script setup>
import Sidebar from '../components/Sidebar.vue'

const meses = ['Jan', 'Fev', 'Mar', 'Abr', 'Mai', 'Jun']
const valores = [80, 90, 190, 260, 300, 90]
const maxValor = 500

const emprestimos = [
  { livro: 'O Pequeno Príncipe', aluno: 'Lucas Ferreira Costa', curso: '1MI1', periodo: 'Manhã', emprestimo: '15/05/2026', devolucao: '30/05/2026', status: 'Atrasado', badge: 'badge-atrasado' },
  { livro: 'O Senhor dos Anéis', aluno: 'Mariana Costa Santos', curso: '2DS3', periodo: 'Noite', emprestimo: '14/05/2026', devolucao: '29/05/2026', status: 'Vencendo', badge: 'badge-vencendo' },
  { livro: '1984', aluno: 'Gabriel Santos Oliveira', curso: '1MI3', periodo: 'Manhã', emprestimo: '16/05/2026', devolucao: '31/05/2026', status: 'No prazo', badge: 'badge-no-prazo' },
  { livro: 'Reinações de Narizinho', aluno: 'Beatriz Oliveira Almeida', curso: '1MI2', periodo: 'Manhã', emprestimo: '25/05/2026', devolucao: '09/06/2026', status: 'No prazo', badge: 'badge-no-prazo' },
  { livro: 'A Hora da Estrela', aluno: 'Rafael Almeida Martins', curso: '2ED2', periodo: 'Noite', emprestimo: '01/06/2026', devolucao: '16/06/2026', status: 'No prazo', badge: 'badge-no-prazo' },
]
</script>

<template>
  <Sidebar page-title="Dashboard" active="dashboard">
    <div class="page-header">
      <h1>Dashboard</h1>
      <div style="display:flex; gap:0.6rem; align-items:center;">
        <button class="btn-outline">Junho 2026</button>
        <button class="btn-outline">Exportar PDF</button>
        <button class="btn-primary-action">Atualizar</button>
      </div>
    </div>

    <div class="stats-grid">
      <div class="stat-card orange">
        <span class="stat-label">Livros Emprestados</span>
        <div class="stat-value">0</div>
      </div>
      <div class="stat-card green">
        <span class="stat-label">Livros Disponíveis</span>
        <div class="stat-value">0</div>
      </div>
      <div class="stat-card blue">
        <span class="stat-label">Total de Livros</span>
        <div class="stat-value">0</div>
      </div>
      <div class="stat-card purple">
        <span class="stat-label">Devolvidos no Mês</span>
        <div class="stat-value">0</div>
      </div>
    </div>

    <div class="charts-grid">
      <div class="chart-card">
        <h3>📊 Empréstimos por Mês</h3>
        <div class="bar-chart">
          <div class="bar-col" v-for="(v, i) in valores" :key="i">
            <div class="bar" :style="{ height: (v / maxValor) * 100 + '%' }"></div>
            <span class="bar-label">{{ meses[i] }}</span>
          </div>
        </div>
      </div>

      <div class="chart-card">
        <h3>🍩 Status do Acervo</h3>
        <div class="donut"></div>
      </div>
    </div>

    <div class="table-card">
      <div class="table-card-header">
        <h3>📋 Últimos Empréstimos Realizados</h3>
        <div class="table-tools">
          <input type="text" placeholder="Filtrar..." />
          <button class="btn-outline">Ver todos</button>
        </div>
      </div>
      <table class="data-table">
        <thead>
          <tr>
            <th>#</th>
            <th>Livro</th>
            <th>Aluno</th>
            <th>Curso</th>
            <th>Período</th>
            <th>Data Empréstimos</th>
            <th>Data Devolução</th>
            <th>Status</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(e, i) in emprestimos" :key="i">
            <td>{{ i + 1 }}</td>
            <td>{{ e.livro }}</td>
            <td>{{ e.aluno }}</td>
            <td>{{ e.curso }}</td>
            <td>{{ e.periodo }}</td>
            <td>{{ e.emprestimo }}</td>
            <td>{{ e.devolucao }}</td>
            <td><span class="badge" :class="e.badge">{{ e.status }}</span></td>
          </tr>
        </tbody>
      </table>
    </div>
  </Sidebar>
</template>