<template>
  <form @submit.prevent="onSubmit">
    <h2 class="label-wrapper">
      <label for="new-todo-input" class="label__lg">
        What needs to be done?
      </label>
    </h2>
    <ul>
      <li>
        <input class="input__lg" type="text" id="new-todo-input" name="new-todo" autocomplete="off"
               v-model.lazy.trim="label"/>
        <button type="submit" class="btn btn__primary btn__lg">Add</button>
      </li>
    </ul>

  </form>

</template>

<script>
export default {
  name: "ToDoForm",
  methods: {
    onSubmit() {
      if (this.label === "") {
        return;
      }
      // console.log("form submitted----:", this.label)
      this.$emit("todo-added", this.label)
      this.label = "";
    }
  },
  data() {
    return {
      label: ""
    }
  }
}
</script>

<style scoped>

</style>