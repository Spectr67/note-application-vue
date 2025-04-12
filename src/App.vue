<script>
import NoteSubmitter from './components/NoteSubmitter.vue'
import NotesCounter from './components/NotesCounter.vue'
import NoteList from './components/NotesList.vue'

export default {
  components: { NoteSubmitter, NotesCounter, NoteList },

  data() {
    return {
      notes: [],
    }
  },
}
</script>

<template>
  {{ notes }}
  <div class="container">
    <div class="section">
      <h1>Приложение для заметок</h1>
    </div>

    <div class="section">
      <NoteSubmitter @note-submitted="notes.push($event)" />
    </div>

    <div class="section">
      <NotesCounter :notes-count="notes.length" />

      <NoteList v-model="notes" />

      <NoteList v-model="notes" />
    </div>
  </div>
</template>
