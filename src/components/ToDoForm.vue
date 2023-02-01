<template>
  <form @submit.prevent="onSubmit">
    <label for="new-todo-input">What needs to be done?</label>
    <ul>
      <li>
        <input type="text" id="new-todo-input" name="new-todo" autocomplete="off" v-model="label"/>
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
      console.log("form submitted----:", this.label)
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