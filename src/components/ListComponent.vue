<template>
  <div>
    <ul>
      <div
        id="list-item"
        v-for="(todoItem, index) in todoListArray"
        :key="index"
      >
        <button
          id="complete-task-btn"
          @click="todoItem.taskStatus = !todoItem.taskStatus"
          :class="{ 'btn-clicked': todoItem.taskStatus }"
        ></button>

        <div id="text-box">
          <p id="title" :class="{ 'task-completed': todoItem.taskStatus }">
            {{ todoItem.taskName }}
          </p>
        </div>
      </div>
    </ul>
  </div>
</template>

<script>
export default {
  name: "divstComponent",
  props: {
    todoListArray: {
      type: Array,
      default: function () {
        return [
          {
            taskName: "No data passed",
            taskStatus: true,
          },
        ];
      },
    },
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  padding: 0;
  margin: auto;
}

#list-item {
  background-color: var(--lighter-background-colour);
  border-radius: 10px;
  padding: 0 25px 0 25px;
  margin: 15px;
}

input {
  border-radius: 50px;
  display: inline;
  width: 20px;
  height: 20px;
}

#text-box {
  padding: 15px 20px 15px 20px;
  display: inline-block;
}

#title {
  font-size: 1rem;
}

#description {
  font-size: 0.8rem;
  color: rgb(87, 87, 87);
}

#complete-task-btn {
  width: 25px;
  height: 25px;
  /*  background-color: var(--lighter-background-colour);*/
  border: 2px solid black;
  border-radius: 50px;
}

.task-completed {
  text-decoration: line-through;
  color: var(--deemphesised-text-colour);
}

.btn-clicked {
  background-color: lightblue;
}
</style>