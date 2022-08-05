<template>
  <div class="todo">
    <h1>ToDoList</h1>
    <input type="text" v-model="task" />
    <button @click="addtask">Submit</button>
    <ul v-for="task in tasks" :key="task.name">
      <li>{{ task.name }}</li>
      <button @click="deletetask(index)">Delete</button>
    </ul>
  </div>
</template>
<script>
export default {
  name: "ToDoList",
  data() {
    return {
      tasks: [],
      task: "",
    };
  },
  methods: {
    addtask() {
      if (this.task.length === 0) return;
      this.tasks.push({ name: this.task });
      this.task = "";
    },
    deletetask(index) {
      this.tasks.splice(index, 1);
    },
  },
};
</script>

<style>
body {
  background-image: url("../assets/pexels-photo-1934846.webp");
  background-repeat: no-repeat;

  background-position: center;
  background-size: 100% 150vh;
}
.todo {
  background-image: url("../assets/pexels-photo-1934846.webp");
  background-repeat: no-repeat;

  background-position: center;
  background-size: 600px 600px;
  background: lightblue;
  width: 600px;
  flex-wrap: wrap;
  height: 600px;
  margin: 10px auto;
  text-align: center;
}
h1 {
  background: black;
  font-size: 40px;
  font-weight: 900;
  color: rgb(255, 255, 255);
}
.todo input {
  width: 300px;
  height: 35px;
  border-bottom: 4px solid red;
  border-top: 4px solid green;
  border-left: 4px solid blue;
  border-radius: 20px;
  text-transform: capitalize;
  font-size: 15px;
  font-weight: 400;
  margin-top: 20px;
}
.todo button {
  width: 100px;
  height: 45px;
  margin: auto;
  font-size: 20px;
  background: yellow;
  color: black;
  font-weight: 500;
  border-bottom: 4px solid red;
  border-top: 4px solid green;
  border-left: 4px solid blue;
  border-radius: 20px;
}
ul {
  display: flex;
  flex-direction: row;
  width: 400px;
  height: 40px;
  justify-content: center;
  text-align: center;
  padding-left: 20px;
  list-style-type: "\1F44D";
  margin: 10px auto;
  padding-top: 30px;
  justify-content: space-around;
}
ul li {
  width: 320px;
  height: 35px;
  text-align: left;
  font-size: 20px;
  padding: 5px 0 0 10px;
  background: white;
  font-weight: 500;
  text-transform: capitalize;
  border-bottom: 4px solid red;
  border-top: 4px solid green;
  border-left: 4px solid blue;
  border-radius: 20px;
}
</style>