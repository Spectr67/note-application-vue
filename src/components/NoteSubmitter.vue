<script>
const makeId = () => ((Math.random() * 0xffff_ffff) >>> 0).toString(16)

const initNote = () => ({
  id: makeId(),
  text: '',
  isEditable: false,
})

export default {
  emits: ['note-submitted'],

  data() {
    return {
      note: initNote(),
    }
  },

  methods: {
    handleClick() {
      if (this.note.text) {
        this.$emit('note-submitted', { ...this.note })
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
