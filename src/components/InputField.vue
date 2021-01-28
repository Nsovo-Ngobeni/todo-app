<template>
  <div id="component-container">
    <div id="centre-elements">
      <input
        id="input-field"
        type="text"
        v-model="currentInput"
        placeholder="Add Task"
      />
      <button id="add-task" @click="addTask">Add</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ListComponent",
  data: function () {
    return {
      currentInput: "",
    };
  },
  props: {
    todoListArray: {
      type: Array,
      required: true,
    },
  },
  methods: {
    addTask() {
      this.todoListArray.unshift({
        taskName: this.currentInput,
        taskStatus: false,
      });
      this.currentInput = "";
    },
  },
};
</script>

<style scoped>
#component-container {
  margin: auto;
  padding: 25px;
}

#input-field {
  padding: 1% 0 1% 2.5%;
  width: 75%;
  margin-right: 2.5%;
  border-radius: 5px;
}

#center-elements {
  width: 100%;
  margin: auto;
}

#add-task {
  width: 10%;
  height: 40px;
  border-radius: 5px;
  background-color: var(--lighter-background-colour);
}
</style>