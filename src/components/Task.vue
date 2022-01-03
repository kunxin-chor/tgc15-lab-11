<template>
  <li class="list-group-item">
    <!-- t is the variable that stores the task object -->
    <h2>{{ task.name }}</h2>
    <ul>
      <li>Urgency: {{ task.urgency }}</li>
      <li>Importance: {{ task.importance }}</li>
      <li>Date Due: {{ task.dateDue }}</li>
    </ul>
    <button class="btn btn-sm btn-primary mx-1">Edit</button>
    <button class="btn btn-sm btn-danger mx-1">Delete</button>
    <button class="btn btn-sm btn-success mx-1">Mark as done</button>
  </li>
</template>

<script>
export default {
  props: ["task"],
};
</script>