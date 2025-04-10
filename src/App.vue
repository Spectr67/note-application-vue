<script>
import noteAdder from './components/noteAdder.vue'
import noteCounter from './components/noteCounter.vue'
import noteList from './components/notesList.vue'

export default {
  components: { noteAdder, noteCounter, noteList },

  data() {
    return {
      notes: [],
    }
  },
}
</script>

<template>
  <div class="container">
    <div class="section">
      <h1>Приложение для заметок</h1>
    </div>

    <div class="section">
      <noteAdder @note-added="notes.push($event)" />
    </div>

    <div class="section">
      <noteCounter :note-counter="notes.length" />

      <noteList v-model="notes" />
    </div>
  </div>
</template>
