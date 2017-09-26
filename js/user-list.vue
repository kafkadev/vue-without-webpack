<template>
<div class="userList">
      <div class="left">
        <h2>User List</h2>
        <p>Buraya Tıkla: {{selectedUser}} </p>
        <ul>
          <li class="userLink" @click="loadUserData(123)">User 123</li>
          <li class="userLink" @click="loadUserData(456)">User 456</li>
        </ul>
      </div>
      <div class="right" v-if="selectedUser.userId">
        <user :user-id="selectedUser.userId" :user-data="selectedUser.userData"></user>
      </div>
    </div>
</template>

<script>
var User = httpVueLoader('./user.vue')
module.exports = {
  data: function data() {
    return {
      selectedUser: {} // selected user data. Place this here to make sure it's reactive.
    };
  },
  methods: {
    loadUserData: function loadUserData(id) {
      this.selectedUser = id === 123 ? { userId: 123 } : { userId: 456, userData: { age: 38, name: 'Patrick' } };
    }
  },

    components: {
      user: User
    }
  }
  </script>

  <style>
  .hello {
    background-color: #ffe;
  }
  </style>

