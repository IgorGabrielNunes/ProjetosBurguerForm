<template>
   <div id="nav">
    <router-link to="/" id="logo-url">
      <img :src="logo" :alt="alt" id="logo">
    </router-link>
    <router-link to="/">Home</router-link> 
    <router-link to="/pedidos">Pedidos</router-link>
    <router-link to="/Cadastro">Cadastro</router-link>
    <router-link to="/Login">Login</router-link>
  </div>

</template>

<script>
export default {
  name: "Navbar",
  props: ["logo", "alt"]
}
</script>

<style scoped>
  #nav {
    background-color: rgb(255, 255, 255);
    border-bottom: 4px solid rgb(255, 0, 0);
    padding: 15px 50px;
    display: flex;
    justify-content: flex-end;
    align-items: center;
  }
  #nav #logo-url {
    margin: auto;
    margin-left: 0%;
  }
  #logo {
    width: 40px;
    height: 40px;
  }
  #nav a {
    color: #000000;
    text-decoration: none;
    margin: 12px;
    transition: .5s;
  }
  #nav a:hover {
    color: rgb(255, 0, 0);

  }
</style>