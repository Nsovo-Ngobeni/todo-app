<template>
  <div>
    <ul>
      <div id="list-item" v-for="(todoItem, index) in todoList" :key="index">
        <input
          type="checkbox"
          @click="todoItem.taskComplete = !todoItem.taskComplete"
        />
        <div id="text-box">
          <p id="title" :class="{ 'line-through': todoItem.taskComplete }">
            {{ todoItem.taskName }}
          </p>
          <p
            id="description"
            :class="{ 'line-through': todoItem.taskComplete }"
          >
            {{ todoItem.taskDescription }}
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
    todoList: {
      type: Array,
      default: function () {
        return [
          {
            taskName: "No data passed",
            taskDescription: "No data has been passed into the todo list",
            taskComplete: true,
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
  height: 27.5px;
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

.line-through {
  text-decoration: line-through;
}
</style>