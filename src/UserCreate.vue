<template>
   <div class="container">
      <h1>KULLANICI GİRİŞ</h1>
      Kullanıcı Adı
      <input v-model="userName" type="text" />
      e-mail
      <input v-model="email" type="text" />
      password
      <input v-model="password" type="text" />
      <button @click="createUser()" class="save">Save</button>
   </div>
</template>

<script>
export default {
   data() {
      return {
         userName: "",
         email: "",
         password: "",
         userList: [],
      };
   },

   methods: {
      createUser() {
         const user = {
            userName: this.userName,
            email: this.email,
            password: this.password,
         };

         this.userList.push(user);
         localStorage.setItem("users", JSON.stringify(this.userList));

         this.clearFrom();
      },

      clearFrom() {
         (this.userName = ""), (this.email = ""), (this.password = "");
      },
   },
};
</script>

<style>
.container {
   display: grid;
   margin-inline: 500px;
   font-family: Avenir, Helvetica, Arial, sans-serif;
   -webkit-font-smoothing: antialiased;
   -moz-osx-font-smoothing: grayscale;
   text-align: left;
   color: #000000;
   margin-top: 60px;
}

.save {
   font-weight: 900;
   width: 100px;
   height: 30px;
   color: white;
   background: rgb(0, 0, 0);
   border: whitesmoke 1px solid;
   border-radius: 20px;
}
</style>
