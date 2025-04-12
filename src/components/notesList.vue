<script>
import NoteItem from './noteItem.vue'

export default {
  components: { NoteItem },

  props: ['modelValue'],

  emits: ['update:model-value'],
}
</script>

<template>
  {{ modelValue }}
  <div class="notes" id="notes-container">
    <noteItem
      v-for="(note, idx) of modelValue"
      :key="idx"
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
          modelValue.filter(t => t !== note)
        )
      "
    />
  </div>
</template>
