<template>
  <div id="app">
    <Kanban :data="data"/>

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
          task:[]
        },
        {
          name:"What?",
          colors:"#FF0099",
          task:[]
        },
        {
          name:"Done",
          colors:"#FF00FF",
          task:[]
        }
      ]
    }
  }

}
</script>

<style>
#app {
  height: 100vh;
  
}
</style>
