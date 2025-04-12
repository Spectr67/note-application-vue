<script>
export default {
  props: ['noteCounter'],
}
</script>
<template>
  <div class="notes-header">
    <h2>Список заметок</h2>
    <span class="notes-count">Всего заметок: {{ noteCounter }}</span>
  </div>
</template>
