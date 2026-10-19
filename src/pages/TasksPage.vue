<template>
  <f7-page name="tasks">
    <f7-navbar title="Мої завдання" />

    <div class="page-content">
      <div class="page-heading">
        <h1>Усі завдання</h1>
        <p>Твій список справ у TaskFlow</p>
      </div>

      <f7-list media-list class="task-list">
        <f7-list-item
          v-for="task in tasks"
          :key="task.id"
          :title="task.title"
          :subtitle="task.description"
        >
          <template #media>
            <i
              class="f7-icons task-icon"
              :class="{ completed: task.completed }"
            >
              {{ task.completed ? 'checkmark_circle_fill' : 'circle' }}
            </i>
          </template>

          <template #after>
            <span
              class="task-status"
              :class="{ 'status-completed': task.completed }"
            >
              {{ task.completed ? 'Виконано' : 'У процесі' }}
            </span>
          </template>
        </f7-list-item>
      </f7-list>
    </div>

    <AppTabbar active="tasks" />
  </f7-page>
</template>

<script setup>
import { tasks } from '../data/tasks.js';
import AppTabbar from '../components/AppTabbar.vue';
</script>
