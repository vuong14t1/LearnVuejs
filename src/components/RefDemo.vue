<template>
  <div class="ref-demo">
      <h1>Demo ref</h1>
      <button class="avatar" @click="handleChangeAvatar">Change avatar</button>
      <input type="file" ref="inputFileAvatar" style="display: none">
  </div>
</template>

<script>
export default {
    name: "RefDemo",
    data() {
        return {};
    },
    methods:{
        handleChangeAvatar(){
            // this.$refs.inputFileAvatar.click
            console.log(this.$refs.inputFileAvatar.getAttribute("type"));
        }
    }
}
</script>

<style>
    .ref-demo {
        margin-top: 20px;
        padding: 100px, 30px;
        border: 1px solid #000000;
        margin-bottom: 50px;
        padding-bottom: 20px;
    }
    .avatar {
        color: #000000;
        padding: 5px;
        background-color: aqua;
    }
    .avatar:hover{
        color: #ffffff;
        background-color: #000000;
    }
</style>