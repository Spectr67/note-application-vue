<script>
const initNote = () => ({
  text: '',
})

export default {
  emits: ['note-added'],

  data() {
    return {
      note: initNote(),
    }
  },

  methods: {
    handleClick() {
      if (this.note.text) {
        this.$emit('note-added', { ...this.note })
        this.note = initNote()
      }
    },
  },
}
</script>

<template>
  <div class="note-form">
    <textarea
      id="note-content"
      rows="4"
      placeholder="Введите вашу заметку..."
      v-model="note.text"
    ></textarea>
    <button @click="handleClick" id="add-note">Добавить заметку</button>
  </div>
</template>
