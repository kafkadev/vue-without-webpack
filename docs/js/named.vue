<template>
  <div>
    <h2>Users loaded into named views:</h2>
    <ul>
      <li>
        <router-link :to="{ name: 'named_id', params: { userId: 123 } }">User 123</router-link>
      </li>
      <li>
        <router-link :to="{ name: 'named_id', params: { userId: 456, userData: { age: 37, name: 'Patrick'} } }">User 456</router-link>
      </li>
      </ul>
      <div class="userList">
        <router-view class="left" name="user_details"></router-view>
        <router-view class="right" name="sidebar"></router-view>
      </div>
    </div>
  </template>

  <script>
  module.exports = {
    name: "named",
    methods: {}
  }
  </script>

  <style>
  .hello {
    background-color: #ffe;
  }
  </style>

