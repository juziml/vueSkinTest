<template>
  <div>
    <!--    v-bind: 可缩写为 :-->
    <input type="checkbox" :id="id" :checked="isDone"/>
    <label :for="id">{{ label }}</label>

  </div>

</template>

<script>
import uniqueId from 'lodash.uniqueid'

export default {
  name: "ToDoItem",
  props: {
    id: {required: true, type: String},
    label: {required: true, type: String},
    done: {default: false, type: Boolean}
  },
  data() {
    return {
      isDone: this.done,
    };
  }
}
</script>

<style scoped>

</style>