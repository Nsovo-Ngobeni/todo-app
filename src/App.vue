<template>
  <div>
    <Header />
    <div id="container">
      <ListComponent :todoList="todoListArray" />
    </div>
  </div>
</template>

<script>
// Import components
import Header from "./components/Header";
import ListComponent from "./components/ListComponent";

export default {
  name: "App",
  data: function () {
    return {
      todoListArray: [
        {
          taskName: "Test Application",
          taskDescription: "Check if this thing works",
          taskComplete: false,
        },
        {
          taskName: "Second Widget Test",
          taskDescription: "Check if the list function is working",
          taskComplete: false,
        },
        {
          taskName: "Third Widget Test",
          taskDescription: "Just to see if this list thing works properly",
          taskComplete: false,
        },
      ],
    };
  },
  components: {
    Header,
    ListComponent,
  },
};
</script>

<style>
:root {
  /* Background colours */
  --main-background-colour: #f0f3f7;
  --darker-background-colour: #d1dad8;
  --darkest-background-colour: #99aca2;
  --lighter-background-colour: #fafcff;

  /* Main colours */
  --main-colour: #d553f1;
  --main-colour-lighter: #eba3dd;
  --main-colour-lightest: #f6cbd0;

  /* Secondary colours */
  --secondary-colour: #6690fb;
  --secondary-colour-lighter: #4cb2f7;
  --secondary-colour-lighest: #4bdaf4;

  /* Text Colours */
  --main-text-colour: #222;
  --deemphesised-text-colour: #bdbdbd;
}

* {
  padding: 0;
  margin: 0;
  font-family: Overpass Mono;
}

body {
  background-color: var(--main-background-colour);
}

#container {
  margin: auto;
  width: 80%;
  padding: 10px 5px 10px 5px;
  background-color: var(--darker-background-colour);
  border-radius: 10px;
  margin: auto;
}
</style>