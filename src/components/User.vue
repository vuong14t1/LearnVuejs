<template>
  <div class="user">
    <p>User component</p>
    <p>Name: {{userClone.name}}</p>
    <p>Age: {{userClone.age}}</p>
    <button @click="handleDelete">Delete</button>
  </div>

</template>

<script>
export default {
    name: "User",
    data() {
        return {
            userClone: this.user
        }
    },
    props:{
        user: Object
    },
    methods: {
        handleDelete() {
            console.log("delete user");
            var data = {
                id: this.user.id
            };
            this.$emit('nameEventDeleteUser', data);
        }
    }
}
</script>

<style>

</style>