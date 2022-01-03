<template>
  <div>
    <ul class="list-group">
      <Task v-for="t in tasks" v-bind:task="t" v-bind:key="t.id" />
    </ul>
    <h2>Add New Task</h2>
    <div>
      <div>
        <label>Task Name:</label>
        <input class="form-control" type="text" v-model="newTask.name" />
      </div>
      <div>
        <label>Urgency:</label>
        <select class="form-control" v-model="newTask.urgency">
          <option value="1">Not urgent</option>
          <option value="2">Somewhat urgent</option>
          <option value="3">Urgent</option>
          <option value="4">Very Urgent</option>
          <option value="5">Super Urgent</option>
        </select>
      </div>
      <div>
        <label>Importance</label>
        <select class="form-control" v-model="newTask.importance">
          <option value="1">Can take your time</option>
          <option value="2">Not important</option>
          <option value="3">Important</option>
          <option value="4">Very Important</option>
          <option value="5">Super Important</option>
        </select>
      </div>
      <div>
        <label>Date Due:</label>
        <input
          class="form-control"
          type="datetime-local"
          v-model="newTask.dateDue"
        />
      </div>
      <button v-on:click="addTask" class="btn btn-primary btn-sm my-3">
        Add New Task
      </button>
    </div>
  </div>
</template>

<script>
import Task from "@/components/Task";

export default {
  data: function () {
    return {
      newTask: {
        name: "",
        ugency: "",
        importance: "",
        dateDue: "",
      },

      tasks: [
        {
          id: 1,
          name: "Wash the car",
          urgency: 5,
          importance: 2,
          dateDue: "2021-12-31",
        },
        {
          id: 2,
          name: "Pay income tax",
          urgency: 3,
          importance: 5,
          dateDue: "2022-04-15",
        },
        {
          id: 3,
          name: "Return library book",
          urgency: 2,
          importance: 2,
          dateDue: "2022-01-02",
        },
      ],
    };
  },
  components: { Task },
  methods: {
    addTask: function () {
      let newTask = {
        // object spread operator
        ...this.newTask,
        id: Math.floor(Math.random() * 10000 + 9999),
      };

      this.tasks.push(newTask);
      this.newTask = {
        name: "",
        importance: "1",
        urgency: "1",
        dateDue: "",
      };
    },
  },
};
</script>