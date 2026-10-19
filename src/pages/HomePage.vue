<template>
  <f7-page name="home">
    <f7-navbar title="TaskFlow">
      <template #right>
        <f7-link href="/about/">
          <i class="f7-icons">info_circle</i>
        </f7-link>
      </template>
    </f7-navbar>

    <div class="page-content">
      <div class="home-header">
        <h1>Мої завдання</h1>
        <p>Плануй свій день ефективно</p>
      </div>

      <div class="stats-grid">
        <div class="stat-card">
          <div class="stat-number">{{ tasks.length }}</div>
          <div class="stat-label">Усього завдань</div>
        </div>

        <div class="stat-card">
          <div class="stat-number">{{ completedCount }}</div>
          <div class="stat-label">Виконано</div>
        </div>
      </div>

      <div class="section-header">
        <h2>Останні завдання</h2>
        <f7-link href="/tasks/">Усі</f7-link>
      </div>

      <f7-list media-list class="task-list">
        <f7-list-item
          v-for="task in recentTasks"
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
        </f7-list-item>
      </f7-list>
    </div>

    <AppTabbar active="home" />
  </f7-page>
</template>

<script setup>
import { computed } from 'vue';
import { tasks } from '../data/tasks.js';
import AppTabbar from '../components/AppTabbar.vue';

const completedCount = computed(
  () => tasks.filter((task) => task.completed).length,
);

const recentTasks = computed(() => tasks.slice(0, 3));
</script>
