<template>
  <section class="section">
    <div class="container">
      <h1 class="title">Notes App</h1>
      <note-form @add-note="addNote" />
      <note-list :notes="notes" />
    </div>
  </section>
</template>

<script>
import NoteForm from './components/NoteForm.vue';
import NoteList from './components/NoteList.vue';

export default {
  components: {
    NoteForm,
    NoteList,
  },
  data() {
    return {
      notes: [],
    };
  },
  methods: {
    addNote(note) {
      this.notes.push(note);
    },
  },
};
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
