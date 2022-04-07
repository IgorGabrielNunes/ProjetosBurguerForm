<template>
  <form id="cadastro-form">
    <div class="input-container">
      <label for="nome">Nome Completo:</label>
      <input
        type="text"
        v-model="nomecompleto"
        placeholder="Digite seu nome!"
      />
    </div>
    <div class="input-container">
      <label for="email">Email:</label>
      <input
        type="text"
        v-model="email"
        placeholder="Digite seu email!"
      />
    </div>

    <div class="input-container">
      <label for="senha">Senha:</label>
      <input
        type="password"
        v-model="senha"
        placeholder="Digite sua senha!"
      />
    </div>

  <div class="input-container">
      <label for="senha">Confirme sua senha:</label>
      <input
        type="password"
        v-model="senha"
        placeholder="Confirme sua senha!"
      />
    </div>

    <div class="input-container">
      <label for="nomeuser">Nome de usuario:</label>
      <input
        type="text"
        v-model="nomeuser"
        placeholder="Digite seu nome de usuario!"
      />
    </div>

    <div class="input-container">
      <input type="submit" class="submit-btn" value="Cadastrar" @click.prevent="createCadastro" />
    </div>
  </form>
</template>

<script>

export default {
  name: "CadastroLogin",
  data() {
      return {

        nomecompleto: null,
        email: null,
        senha: null,
        nomeuser: null
      }
    },
  methods: {
  async getDadosCadastro() {
    const req = await fetch("http://localhost:3000/dadoscadastro");
    const data = await req.json();

    this.nomecompleto = data.nomecompleto;
    this.email = data.email;
    this.senha = data.senha;
    this.nomeuser = data.nomeuser;
    },
  async createCadastro (e) {
      
      e.preventDefault()

      const data = {
        nomecompleto: this.nomecompleto,
        email: this.email,
        senha: this.senha,
        nomeuser: this.nomeuser,
        status: "Criado!"
      }

    const dataJson = JSON.stringify(data);
       
        const req = await fetch("http://localhost:3000/usuarios", {
          method: "POST",
        headers: { "Content-Type" : "application/json" },
        body: dataJson
       });

    },
  }
}
</script>

<style scoped>
#cadastro-form {
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
  font-weight: bold;
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
