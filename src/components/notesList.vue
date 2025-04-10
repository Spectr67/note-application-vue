<script>
import noteItem from './noteItem.vue'

export default {
  components: { noteItem },

  props: ['modelValue'],

  emits: ['update:model-value'],
}
</script>

<template>
  <div class="notes" id="notes-container">
    <noteItem
      v-for="(note, idx) of modelValue"
      :key="idx"
      :note="note"
      @remove-note="
        $emit(
          'update:model-value',
          modelValue.filter(t => t !== note)
        )
      "
    />
  </div>
</template>
