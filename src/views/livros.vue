<script setup>
import Sidebar from '../components/Sidebar.vue'

const livros = [
  { titulo: 'Dom Casmurro', autor: 'Machado de Assis', categoria: 'Romance', isbn: '978-85-260-0611-5', exemplares: 5, disponiveis: 2, status: 'Disponível', badge: 'badge-disponivel' },
  { titulo: '1984', autor: 'George Orwell', categoria: 'Ficção Científica', isbn: '978-85-359-0277-2', exemplares: 4, disponiveis: 0, status: 'Emprestado', badge: 'badge-emprestado' },
  { titulo: 'A Hora da Estrela', autor: 'Clarice Lispector', categoria: 'Romance', isbn: '978-85-260-0587-3', exemplares: 3, disponiveis: 3, status: 'Disponível', badge: 'badge-disponivel' },
  { titulo: 'Iracema', autor: 'José de Alencar', categoria: 'Romance', isbn: '978-85-08-04890-1', exemplares: 2, disponiveis: 0, status: 'Emprestado', badge: 'badge-emprestado' },
  { titulo: 'O Alquimista', autor: 'Paulo Coelho', categoria: 'Ficção', isbn: '978-85-325-1229-0', exemplares: 6, disponiveis: 4, status: 'Disponível', badge: 'badge-disponivel' },
]
</script>

<template>
  <Sidebar page-title="Livros" active="livros">
    <div class="page-header">
      <h1>Livros</h1>
      <button class="btn-primary-action">Cadastrar Livro</button>
    </div>

    <div class="filter-bar">
      <input type="text" placeholder="Pesquisar por título, autor ou ISBN..." />
      <select><option>Todas as categorias</option></select>
      <select><option>Todos os status</option></select>
    </div>

    <div class="table-card">
      <table class="data-table">
        <thead>
          <tr>
            <th>Título</th>
            <th>Autor</th>
            <th>Categoria</th>
            <th>ISBN</th>
            <th>Exemplares</th>
            <th>Disponíveis</th>
            <th>Status</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(l, i) in livros" :key="i">
            <td>{{ l.titulo }}</td>
            <td>{{ l.autor }}</td>
            <td>{{ l.categoria }}</td>
            <td>{{ l.isbn }}</td>
            <td>{{ l.exemplares }}</td>
            <td>{{ l.disponiveis }}</td>
            <td><span class="badge" :class="l.badge">{{ l.status }}</span></td>
          </tr>
        </tbody>
      </table>
    </div>
  </Sidebar>
</template>