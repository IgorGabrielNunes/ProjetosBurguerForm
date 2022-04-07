<template>
    <form id="login-form" @submit="loginForm">

      <div class="input-container">
      <label>Digite seu email:</label>
      <input
        type="text"
        v-model="email"
        placeholder="Digite seu email!"
      />
      </div>
      
      <div class="input-container">
      <label>Digite sua senha:</label>
      <input
        type="text"
        v-model="senha"
        placeholder="Digite sua senha!"
      />
      </div>

      <div class="input-container">
      <input type="submit" class="submit-btn" value="Login" />
    </div>
    </form>
</template>

 <script>
 
 export default {
   name: "LoginPage",
   
   data () {
     return {
       email : null,
       senha: null
     }
   }
 }
 </script>

 <style scoped>
#login-form {
  max-width: 300px;
  margin: 0 auto;
}

.input-container {
  display: flex;
  flex-direction: column;
  margin-bottom: 20px;
}

label {
  font-weight: bold;
  margin-bottom: 15px;
  color: black;
  padding: 5px 10px;
  border-left: 4px solid #fc0303;
}
input,
select {
  padding: 5px 10px;
  width: 300px;
  margin: auto;
}

.submit-btn {
  background-color: rgb(255, 0, 0);
  color: #ffffff;
  font-weight: bodl;
  border: 2px solid rgb(255, 0, 0);
  padding: 10px;
  font-size: 16px;
  margin: 0 auto;
  cursor: pointer;
  transition: 0.5s;
}
.submit-btn:hover {
  background-color: transparent;
  color: rgb(0, 0, 0);
}
</style>
