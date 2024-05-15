<template>
  <section class="task-list">
    <h2>Daftar Tugas</h2>
    <div class="task-table">
      <div class="task-header">
        <div class="title">Judul</div>
        <div class="actions">Aksi</div>
      </div>
      <div v-for="task in tasks" :key="task.id" class="task-row">
        <div class="title">{{ task.title }}</div>
        <div class="actions">
          <button @click="editTask(task)">Edit</button>
          <button @click="deleteTask(task.id)">Hapus</button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const tasks = ref([
  { id: 1, title: 'Tugas Contoh', description: 'Ini adalah tugas contoh.' }
])

const editTask = (task: any) => {
  // Logika untuk mengedit tugas
}

const deleteTask = (taskId: number) => {
  // Logika untuk menghapus tugas
}
</script>

<style scoped>
.task-list {
  width: 90%; /* Ubah lebar task-list */
  max-width: 800px; /* Atur maksimum lebar task-list */
  background-color: rgba(255, 255, 255, 0.8);
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: left;
  margin-bottom: 20px; /* Tambah margin bottom */
}

h2 {
  margin-bottom: 20px;
}

.task-table {
  display: flex;
  flex-direction: column;
}

.task-header {
  display: flex;
  justify-content: space-between;
  background-color: #42b983;
  color: white;
  padding: 10px;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
}

.task-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  border-bottom: 1px solid #ddd;
}

.task-row:last-child {
  border-bottom: none;
}

.title {
  flex: 1;
}

.actions {
  min-width: 100px;
  display: flex;
  justify-content: space-between;
}
</style>
