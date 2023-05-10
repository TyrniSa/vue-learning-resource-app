<template>
  <base-dialog v-if="inputIsInvalid" title="Invalid input" @closeDialog="confirmError">
    <template #default>
      <p>All fields are required, please fill all the fields.</p>
    </template>
    <template #actions>
      <base-button @click="confirmError" class="flat"> OK</base-button>
    </template>
  </base-dialog>
  <base-card>
    <form @submit.prevent="submitData">
      <div class="form-control">
        <label for="title">Title</label>
        <input id="title" name="title" type="text" ref="titleInput" />
      </div>
      <div class="form-control">
        <label for="desc">Description</label>
        <textarea id="desc" name="desc" rows="3" ref="descInput"></textarea>
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input id="link" name="link" type="url" ref="linkInput" />
      </div>
      <div>
        <base-button type="submit" class="flat">Add resource</base-button>
      </div>
    </form>
  </base-card>
</template>

<script>
export default {
  inject: ['addResource'],
  data() {
    return {
      inputIsInvalid: false,
    };
  },
  methods: {
    submitData() {
      const enteredTitle = this.$refs.titleInput.value;
      const enteredDesc = this.$refs.descInput.value;
      const enteredLink = this.$refs.linkInput.value;

      if (
        enteredTitle.trim() === '' ||
        enteredDesc.trim() === '' ||
        enteredLink.trim() === ''
      ) {
        this.inputIsInvalid = true;
        return;
      }

      this.addResource(enteredTitle, enteredDesc, enteredLink);
      this.$refs.titleInput.value = '';
      this.$refs.descInput.value = '';
      this.$refs.linkInput.value = '';
    },
    confirmError(){
      this.inputIsInvalid = false;
    }
  },
};
</script>

<style scoped>
form {
  width: 80%;
  padding: 0rem 2rem;
}
label {
  display: block;
  margin-bottom: 0.5rem;
}
input,
textarea {
  display: block;
  width: 100%;
  font-family: 'Roboto', sans-serif;
  padding: 0.5rem;
  border: none;
  border-bottom: 1px solid rgba(0, 0, 0, 0.2);
}
input:focus,
textarea:focus {
  outline: none;
  border-color: #c57f1e;
  background-color: #ece6de;
}
.form-control {
  margin: 1.5rem 0;
}
</style>
