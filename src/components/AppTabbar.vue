<template>
  <f7-toolbar bottom tabbar class="app-tabbar">
    <f7-link
      href="/"
      tab-link
      :tab-link-active="active === 'home'"
    >
      <i class="f7-icons">house_fill</i>
      <span class="tabbar-label">Головна</span>
    </f7-link>

    <f7-link
      href="/tasks/"
      tab-link
      :tab-link-active="active === 'tasks'"
    >
      <i class="f7-icons">square_list_fill</i>
      <span class="tabbar-label">Завдання</span>
    </f7-link>

    <f7-link
      href="/about/"
      tab-link
      :tab-link-active="active === 'about'"
    >
      <i class="f7-icons">info_circle_fill</i>
      <span class="tabbar-label">Про нас</span>
    </f7-link>
  </f7-toolbar>
</template>

<script setup>
defineProps({
  active: {
    type: String,
    default: 'home',
  },
});
</script>
