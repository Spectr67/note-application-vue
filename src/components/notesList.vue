<script>
import NoteItem from './NoteItem.vue'

export default {
  components: { NoteItem },

  props: ['modelValue'],

  emits: ['update:model-value'],
}
</script>

<template>
  {{ modelValue }}
  <div class="notes" id="notes-container">
    <NoteItem
      v-for="note of modelValue"
      :key="note.id"
      :note="note"
      @update-note="
        $emit(
          'update:model-value',
          modelValue.map(mv => (mv.id === $event.id ? $event : mv))
        )
      "
      @remove-note="
        $emit(
          'update:model-value',
          modelValue.filter(t => t.id !== note.id)
        )
      "
    />
  </div>
</template>
