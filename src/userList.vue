<template>
   <div>
      <div class="user-list">
         <h2>user</h2>
         <h2>password</h2>
         <h2>email</h2>
      </div>
      <div v-for="item in userList" class="user-list">
         <p>{{ item.userName }}</p>
         <p>{{ item.password }}</p>
         <p>{{ item.email }}</p>
      </div>
   </div>
</template>

<script>
export default {
   data() {
      return {
         userList: [],
      };
   },
   methods: {
      getUserList() {
         const userList = localStorage.getItem("users");

         if (userList) {
            this.userList = JSON.parse(userList);
         }
      },
   },

   created() {
      this.getUserList();
   },
};
</script>

<style>
.user-list {
   display: grid;
   grid-template-columns: 300px 300px 300px;
}
</style>
