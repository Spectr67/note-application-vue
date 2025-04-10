<script>
export default {
  props: ['note'],

  emits: ['remove-note', 'update-note'],
}
</script>
<template>
  <div class="note-card">
    <div class="note-content">
      <textarea @dblclick="$emit('update-todo', $event.target.value)">{{
        note.text
      }}</textarea>
    </div>
    <div class="note-actions">
      <button @click="$emit('remove-note', note)">Удалить</button>
    </div>
  </div>
</template>
