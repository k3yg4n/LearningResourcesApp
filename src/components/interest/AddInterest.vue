<template>
  <base-card>
    <h2>Add New Interest</h2>
    <form @submit.prevent="addNewInterest">
      <div class="form-control">
        <label for="title">Title: </label>
        <input id="title" name="title" type="text" ref="newTitle" />
      </div>
      <div class="form-control">
        <label for="description">Description: </label>
        <textarea
          id="description"
          name="description"
          rows="3"
          ref="newDesc"
        ></textarea>
      </div>
      <div class="form-control">
        <label for="link">Link: </label>
        <input id="link" name="link" type="url" ref="newLink" />
      </div>
      <div>
        <base-button type="submit">Add Interest</base-button>
      </div>
    </form>
  </base-card>
</template>

<script>
export default {
  inject: ['addInterest'],
  methods: {
    addNewInterest() {
      const newTitle = this.$refs.newTitle.value;
      const newDesc = this.$refs.newDesc.value;
      const newLink = this.$refs.newLink.value;

      if (newTitle === '' || newDesc === '' || newLink === '') {
        alert('ERROR: Please fill out all fields.');
      } else {
        this.addInterest(newTitle, newDesc, newLink);
      }
    },
  },
};
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>
