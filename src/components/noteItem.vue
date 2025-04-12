<script>
export default {
  props: ['note'],

  emits: ['remove-note', 'update-note'],
}
</script>
<template>
  <div class="note-card">
    <div class="note-content">
      <p
        v-if="!note.isEditable"
        @dblclick="$emit('update-note', { ...note, isEditable: true })"
      >
        {{ note.text }}
      </p>
      <textarea
        v-else
        :value="note.text"
        @blur="
          $emit('update-note', {
            ...note,
            text: $event.target.value,
            isEditable: false,
          })
        "
        autofocus
      ></textarea>
    </div>
    <div class="note-actions">
      <button @click="$emit('remove-note')">Удалить</button>
    </div>
  </div>
</template>
