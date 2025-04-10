<script>
export default {
  props: ['note'],

  emits: ['remove-note', 'update-note'],
}
</script>
<template>
  <div class="note-card">
    <div class="note-content">
      <textarea
        :value="note.text"
        @dblclick="$emit('update-note', { ...note, text: $event.target.value })"
      >
      </textarea>
    </div>
    <div class="note-actions">
      <button @click="$emit('remove-note', note)">Удалить</button>
    </div>
  </div>
</template>
