<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    
    <comp-header />
    <list-user :listUser = "listUser" :title='title' @customChangeTitle = 'handleChangeTitle' @eventNameDeleteUser = 'handleDeleteUser'/>
    <button @click="changeData()">Change data parent</button>
    <ref-demo />
  </div>
</template>

<script>
import CompHeader from './components/CompHeader.vue'
import ListUser from './components/ListUser.vue'
import RefDemo from './components/RefDemo.vue'

export default {
  name: 'App',
  data () {
    return {
      title: "Hello vue js",
      listUser: [
        {
          id: 1,
          name: '1',
          age: 2
        },
        {
          id: 2,
          name: '2',
          age: 2
        },
        {
          id: 3,
          name: '3',
          age: 2
        }
      ]
    };
  },
  components: {
    CompHeader,
    ListUser,
    RefDemo
  },
  methods: {
    changeData(){
        this.title = 'Learn vue js simple';
    },
    handleChangeTitle(msg) {
      this.title = msg;
      console.log("parent change title");
    },
    handleDeleteUser(data){
      var idx = this.listUser.findIndex(function (o) {
        return o.id == data.id;
      });
      this.listUser.splice(idx, 1);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
