<script>
import NoteSubmitter from './components/NoteSubmitter.vue'
import noteCounter from './components/noteCounter.vue'
import noteList from './components/notesList.vue'

export default {
  components: { NoteSubmitter, noteCounter, noteList },

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
      <noteCounter :note-counter="notes.length" />

      <noteList v-model="notes" />
    </div>
  </div>
</template>
