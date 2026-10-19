<template>
  <f7-page name="about">
    <f7-navbar title="Про TaskFlow">
      <template #left>
        <f7-link href="/">
          <i class="f7-icons">arrow_left</i>
        </f7-link>
      </template>
    </f7-navbar>

    <div class="page-content">
      <div class="about-header">
        <div class="about-icon">
          <i class="f7-icons">checkmark_alt_circle_fill</i>
        </div>

        <h1>TaskFlow</h1>
        <p>Твій помічник у плануванні</p>
      </div>

      <f7-card>
        <f7-card-content>
          <h2>Про застосунок</h2>
          <p>
            TaskFlow — це простий PWA-застосунок для організації
            щоденних завдань, контролю їх виконання та планування
            власного часу.
          </p>
        </f7-card-content>
      </f7-card>

      <f7-card>
        <f7-card-content>
          <h2>Можливості</h2>
          <f7-list>
            <f7-list-item title="Перегляд списку завдань">
              <template #media>
                <i class="f7-icons">list_bullet</i>
              </template>
            </f7-list-item>

            <f7-list-item title="Контроль виконання">
              <template #media>
                <i class="f7-icons">checkmark_circle</i>
              </template>
            </f7-list-item>

            <f7-list-item title="Адаптивний інтерфейс">
              <template #media>
                <i class="f7-icons">device_phone_portrait</i>
              </template>
            </f7-list-item>
          </f7-list>
        </f7-card-content>
      </f7-card>

      <AppTabbar active="about" />
    </div>
  </f7-page>
</template>

<script setup>
import AppTabbar from '../components/AppTabbar.vue';
</script>
