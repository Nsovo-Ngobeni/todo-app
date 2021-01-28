<template>
  <div>
    <Header />
    <div id="container">
      <InputField :todoListArray="todoListArray" />
    </div>
    <div id="container" v-if="todoListArray[0] != (null || undefined)">
      <ListComponent :todoListArray="todoListArray" />
    </div>
  </div>
</template>

<script>
// Import components
import Header from "./components/Header";
import InputField from "./components/InputField";
import ListComponent from "./components/ListComponent";

export default {
  name: "App",
  data: function () {
    return {
      todoListArray: [],
    };
  },
  components: {
    Header,
    InputField,
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
  --main-colour: lightblue;

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
  font-family: "Poppins", sans-serif;
}

body {
  background-color: var(--main-background-colour);
}

#container {
  margin: 25px auto auto auto;
  width: 80%;
  padding: 10px 5px 10px 5px;
  background-color: var(--darker-background-colour);
  border-radius: 10px;
}
</style>