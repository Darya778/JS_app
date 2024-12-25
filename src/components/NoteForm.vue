<template>
  <form @submit.prevent="handleSubmit">
    <div class="field">
      <label class="label">Title</label>
      <div class="control">
        <input v-model="title" class="input" type="text" placeholder="Note Title" />
      </div>
    </div>

    <div class="field">
      <label class="label">Priority</label>
      <div class="control">
        <div class="select">
          <select v-model="priority">
            <option>Low</option>
            <option>Medium</option>
            <option>High</option>
          </select>
        </div>
      </div>
    </div>

    <div class="field">
      <div class="control">
        <label class="checkbox">
          <input type="checkbox" v-model="completed" />
          Completed
        </label>
      </div>
    </div>

    <div class="field">
      <label class="label">Category</label>
      <div class="control">
        <label class="radio">
          <input type="radio" value="Personal" v-model="category" />
          Personal
        </label>
        <label class="radio">
          <input type="radio" value="Work" v-model="category" />
          Work
        </label>
      </div>
    </div>

    <div class="field">
      <div class="control">
        <button class="button is-primary" type="submit">Add Note</button>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      title: '',
      priority: 'Low',
      completed: false,
      category: 'Personal',
    };
  },
  methods: {
    handleSubmit() {
      if (!this.title.trim()) {
        alert('Title is required!');
        return;
      }
      const note = {
        title: this.title,
        priority: this.priority,
        completed: this.completed,
        category: this.category,
      };
      this.$emit('add-note', note);
      this.title = '';
      this.priority = 'Low';
      this.completed = false;
      this.category = 'Personal';
    },
  },
};
</script>
