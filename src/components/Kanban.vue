<template>
  <div class="kanban">
    <div
      class="column"
      :style="{ backgroundColor: column.colors }"
      v-for="(column, index) in data"
      :key="index"
    >
      <div class="column-header">{{ column.name }}</div>
      <div class="column-body">
        <div class="create-task" @click="create_task(index)">Create Task</div>
      </div>
    </div>
    <b-modal ref="create-task-modal" title="Create Task">
      <p class="my-4">Hello from modal!</p>
    </b-modal>
  </div>
</template>

<script>
export default {
  props: {
    data: Array,
  },
  methods: {
    create_task(index_column) {
        console.log(index_column);
     this.$refs["create-task-modal"].show()
    },
  },
};
</script>

<style>
.kanban {
  background-color: pink;
  width: 100%;
  height: 100%;
}
.column {
  height: 600px;
  width: 300px;
  border-radius: 10px;
  display: inline-block;
  margin: 25px;
  -webkit-box-shadow: 10px 24px 35px 8px rgba(31, 15, 31, 1);
  -moz-box-shadow: 10px 24px 35px 8px rgba(31, 15, 31, 1);
  box-shadow: 10px 24px 35px 8px rgba(31, 15, 31, 1);
  padding: 10px;
}
.column-header {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 50px;
  font-size: 32px;
  font-weight: bold;
}
.column-body {
  height: calc(100% - 50px);
  border-radius: 10px;
  padding: 5px;
  background-color: rgba(255, 255, 255, 0.575);
}
.create-task {
  width: 100%;
  height: auto;
  padding: 10px;
  border-radius: 5px;
  font-size: 18px;
  cursor: pointer;
}
.create-task:hover {
  background-color: white;
}
</style>