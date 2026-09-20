<script setup>
import Sidebar from '../components/Sidebar.vue'

const alunos = [
  { rm: '10705', nome: 'Lucas Ferreira Costa', curso: '1MI', periodo: 'Manhã', email: 'lucas@escola.edu', emprestimos: '2 ativos', status: 'Ativo', badge: 'badge-ativo' },
  { rm: '10710', nome: 'Mariana Costa Santos', curso: '2DS', periodo: 'Tarde', email: 'mariana@escola.edu', emprestimos: '1 ativo', status: 'Ativo', badge: 'badge-ativo' },
  { rm: '10715', nome: 'Beatriz Oliveira Almeida', curso: '3MI', periodo: 'Noite', email: 'beatriz@escola.edu', emprestimos: '3 ativos', status: 'Bloqueado', badge: 'badge-bloqueado' },
  { rm: '10720', nome: 'Gabriel Santos Oliveira', curso: '2MI', periodo: 'Manhã', email: 'gabriel@escola.edu', emprestimos: '1 ativo', status: 'Ativo', badge: 'badge-ativo' },
  { rm: '10725', nome: 'Rafael Almeida Martins', curso: '2ED', periodo: 'Manhã', email: 'rafael@escola.edu', emprestimos: '2 ativos', status: 'Ativo', badge: 'badge-ativo' },
  { rm: '10730', nome: 'Thiago Rodrigues Pereira', curso: '1EF', periodo: 'Tarde', email: 'thiago@escola.edu', emprestimos: '1 ativo', status: 'Bloqueado', badge: 'badge-bloqueado' },
]
</script>

<template>
  <Sidebar page-title="Alunos" active="alunos">
    <div class="page-header">
      <h1>Alunos</h1>
      <button class="btn-primary-action">Cadastrar Aluno</button>
    </div>

    <div class="filter-bar">
      <input type="text" placeholder="Pesquisar por nome, RA ou curso..." />
      <select><option>Todos os status</option></select>
      <select><option>Todos os períodos</option></select>
    </div>

    <div class="table-card">
      <table class="data-table">
        <thead>
          <tr>
            <th>RM</th>
            <th>Nome</th>
            <th>Curso</th>
            <th>Período</th>
            <th>E-mail</th>
            <th>Empréstimos</th>
            <th>Status</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(a, i) in alunos" :key="i">
            <td>{{ a.rm }}</td>
            <td>{{ a.nome }}</td>
            <td>{{ a.curso }}</td>
            <td>{{ a.periodo }}</td>
            <td>{{ a.email }}</td>
            <td><span class="badge badge-ativos">{{ a.emprestimos }}</span></td>
            <td><span class="badge" :class="a.badge">{{ a.status }}</span></td>
          </tr>
        </tbody>
      </table>
    </div>
  </Sidebar>
</template>