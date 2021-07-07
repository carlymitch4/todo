<template>
  <div>
    <h3>Task manager</h3>
    <div class="add">
      <form @submit="onSubmit">
        <input type="text" v-model="title" placeholder="Add task here...">
        <input type="submit" value="Submit">
      </form>
    </div>
  </div>
</template>

<script>
import { mapActions } from 'vuex'

export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    ...mapActions(['addTodo']),
    onSubmit(e) {
      e.preventDefault()
      this.addTodo(this.title)
    }
  }
}
</script>

<style scoped>
form {
  display: flex;
}

input[type="text"] {
  flex: 10;
  padding: 10px;
  border: 1px solid #3AAFB9;
  outline: 0;
  border-radius: 5px 0px 0px 5px;
}

input[type="submit"] {
  flex: 2;
  background: #3AAFB9;
  color: #fff;
  border: 1px #3AAFB9 solid;
  cursor: pointer;
  border-radius: 0px 5px 5px 0px;
}
</style>