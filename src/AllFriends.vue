<template>
<div id="all-friends">
  <h2>All Friends</h2>
  <div v-for="(friend, index) in friends" :key="index">
    <span @click="unfriend(friend.name)">{{friend.name}}</span> <!--@click event sends to unfriend method line 36-->
  </div>
</div>
</template>

<script>
export default {
  name: 'AllFriends',
  props: ['friends'],
  data() {
    return {
      friends: [{
          name: 'Mario',
          online: true
        },
        {
          name: 'Luigi',
          online: false
        },
        {
          name: 'Toad',
          online: true
        },
        {
          name: 'Bowser',
          online: false
        }
      ]
    };
  },
  methods: {
    unfriend(name){ // unfriend method emits name, delete name. Goto App.vue 5 AllFriends component listens to emitted event w @delete
      this.$emit('delete', {name})
    }
  }
};
</script>

<style>
</style>
