<template>
  <div id="app">
    <Kanban :data="data" :create_task_submit ="create_task_submit"/>

  </div>
</template>

<script>
import Kanban from "./components/Kanban"


export default {
  name: 'App',
  components: {
    Kanban
  
  },

  data(){
    return{
      data:[
        {
          name:"Todo",
          colors:"#FF0066",
          task:[
            {
            task_name: "test"
          }
          ]
        },
        {
          name:"What?",
          colors:"#FF0099",
          task:[      {
            task_name: "test"
          }]
        },
        {
          name:"Done",
          colors:"#FF00FF",
          task:[      {
            task_name: "test"
          }]
        }
      ]
    }
  },
  methods :{
    create_task_submit(column_index,item){
      this.data[column_index].task.push(item)
    }
  }

}
</script>

<style>
#app {
  height: 100vh;
  
}
</style>
