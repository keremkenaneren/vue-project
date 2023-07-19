<template>
   <div class="container">
      <h1>Insider</h1>
      <input type="email" name="email" class="email" v-model="email" />
      <input type="password" name="password" v-model="password" />
      <button @click="login()" class="save">SAVE</button>
      <p>{{ warningMessage }}</p>
   </div>
</template>

<script>
export default {
   data() {
      return {
         email: "",
         password: "",
         warningMessage: "",
      };
   },
   methods: {
      login() {
         if (this.email == "" || this.password == "") {
            this.warningMessage = "Lütfen tüm alanları doldurunuz !!";

            return;
         }

         this.warningMessage = "";

         if (this.email.includes("@") === false) {
            this.warningMessage = "Lütfen geçerli bir email adresi girin !!";

            return;
         } else if (this.email === "a@" && this.password === "1") {
            this.$router.push("/userCreate");
         } else {
            this.warningMessage = "Hatalı Giriş !";
         }
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

input {
   background: rgb(187, 180, 181);
   margin-bottom: 5%;
   width: 300px;
   height: 20px;
   border: whitesmoke 1px solid;
   border-radius: 5px;
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
.save:hover {
   background: rgb(68, 68, 68);
}
</style>
