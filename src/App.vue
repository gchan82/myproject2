<template>
<div id="app">
  <h1>{{title}}</h1>
  <Navbar />
  <AllFriends :friends="friends" @delete="deleteFriend"/> <!-- :data bind & pass down friends as prop in AllFriends component, from "friends" data on this page. @delete listens to emited event from AllFriends.vue line 36-37 - calls method "deleteFriend"-->
  <OnlineFriends :friends="friends" />
</div>
</template>

<script>
import Navbar from './Navbar.vue'
import AllFriends from './AllFriends.vue'
import OnlineFriends from './OnlineFriends.vue'

export default {
  name: 'app',
  components: {
    Navbar,
    OnlineFriends,
    AllFriends
  },
  data() {
    return {
      title: 'My first vue App',
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
      ]}
  },
      methods: {
        deleteFriend(payload){
          console.log(payload)
        }
      }
}
</script>

<style>
h1 {
  color: #444;
  font-weight: normal;
  text-align: center;
}
</style>
