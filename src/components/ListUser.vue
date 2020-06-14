<template>
  <div class="list-user">
      <p>{{title}}</p>
      <p>List user component</p>
      <button @click="customChangeTitle" >button list user</button>
      <user v-for="user in listUser" v-bind:key = "user.id" :user="user" @nameEventDeleteUser = 'handleDeleterUser'/>

  </div>
</template>

<script>
import User from './User.vue';
export default {
    name: 'list-user',
    data() {
        return {

        };
    },
    components: {
        User
    },
    props:{
        title: String,
        listUser: Array
    },
    methods: {
        changeTitle() {
            console.log(this);
        },
        customChangeTitle() {
            console.log('change child title');
            this.$emit('customChangeTitle', 'Title 1111111111111111');
        },
        handleDeleterUser(data) {
            console.log('handleDeleterUser');
            this.$emit('eventNameDeleteUser', data);
        }
    }
}
</script>

<style>

</style>