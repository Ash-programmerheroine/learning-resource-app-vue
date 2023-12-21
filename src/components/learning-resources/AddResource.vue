<template>
    <base-card>
    <form @submit.prevent="submitData">
      <div class="form-control">
        <label for="title">Title</label>
        <input type="text" name="title" id="title" ref="titleInput">
      </div>
      <div class="form-control">
        <label for="title">Description</label>
       <textarea name="description" id="description" ref="descInput" cols="30" rows="3"></textarea>
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input type="url" name="link" id="link" ref="linkInput">
      </div>
      <div>
        <base-button type="submit">Add Resource</base-button>
      </div>
    </form>
    </base-card>
</template>

<script>
export default {
  inject: ['addResource'],
  methods:{
   
    submitData(){
       try{   
      const enteredTitle = this.$refs.titleInput.value;
      const enteredDescription = this.$refs.descInput.value;
      const enteredUrl = this.$refs.linkInput.value;
      this.addResource(enteredTitle, enteredDescription, enteredUrl);
      }
      catch(error){
        console.error('Error in submitData:', error);
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