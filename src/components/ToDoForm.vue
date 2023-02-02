<template>
  <form @submit.prevent="onSubmit">
    <label for="new-todo-input">What needs to be done?</label>
    <ul>
      <li>
        <input type="text" id="new-todo-input" name="new-todo" autocomplete="off" v-model.lazy.trim="label"/>
        <button type="submit">Add</button>
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