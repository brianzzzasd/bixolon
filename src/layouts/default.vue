<script setup>
const route = useRoute()
</script>

<template>
  <div>
    <TheHeader v-if="route.path !== '/login'" />
    <RouterView />
    <TheFooter v-if="route.path !== '/login'" />
  </div>
</template>
