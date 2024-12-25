<template>
  <div>
    <h2 class="subtitle">Your Notes</h2>
    <div v-if="notes.length === 0">No notes available</div>
    <ul>
      <li v-for="(note, index) in notes" :key="index" class="box">
        <p><strong>{{ note.title }}</strong></p>
        <p>Priority: {{ note.priority }}</p>
        <p>Completed: {{ note.completed ? 'Yes' : 'No' }}</p>
        <p>Category: {{ note.category }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    notes: {
      type: Array,
      required: true,
    },
  },
};
</script>
