<script setup>
defineProps({ name: { type: String, required: true } })

const paths = {
  engine: 'M4 13h2V9h3V7h2V5h6v2h2v2h2v4h1v4h-2v2h-3v-2H9v2H6v-2H4v-4Zm4-4v4h8V9H8Z',
  wrench: 'M14.7 6.3a4 4 0 0 0-5.4 5.4L4 17l3 3 5.3-5.3a4 4 0 0 0 5.4-5.4l-2.4 2.4-2-2 2.4-2.4Z',
  brake: 'M12 3a9 9 0 1 0 9 9h-3a6 6 0 1 1-6-6V3Zm0 5a4 4 0 1 0 4 4h-2a2 2 0 1 1-2-2V8Z',
  bolt: 'M13 2 4 14h6l-1 8 9-12h-6l1-8Z',
  clipboard: 'M9 3h6v2h3v16H6V5h3V3Zm1 2v1h4V5h-4ZM8 11h8v2H8v-2Zm0 4h8v2H8v-2Z',
  shield: 'M12 2 4 5v6c0 5 3.4 8.9 8 11 4.6-2.1 8-6 8-11V5l-8-3Zm-1 13-3-3 1.4-1.4L11 12.2l4.6-4.6L17 9l-6 6Z',
  tyre: 'M12 2a10 10 0 1 0 10 10A10 10 0 0 0 12 2Zm0 5a5 5 0 1 1-5 5 5 5 0 0 1 5-5Zm0 2a3 3 0 1 0 3 3 3 3 0 0 0-3-3Z',
  gauge: 'M12 3a9 9 0 0 0-9 9h2a7 7 0 1 1 14 0h2a9 9 0 0 0-9-9Zm0 5-3 5 5-2Z',
}
</script>

<template>
  <svg class="s-icon" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path :d="paths[name]" fill="currentColor" />
  </svg>
</template>

<style scoped>
.s-icon{ width:26px; height:26px; }
</style>
