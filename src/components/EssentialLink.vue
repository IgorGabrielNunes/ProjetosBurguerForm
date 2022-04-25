
<script setup>
import { useQuasar } from "quasar";
import { ref, computed, reactive } from "vue";
const $q = useQuasar();
const carrinho = ref([]);

const produtos = [
  {
    id: 1, 
    name: "Monitor Gamer LG",
    desc: "Monitor Gamer, 24 polegas Full HD 144 Gh", 
    imagem: "/imgs/monitores/1.jpg",
    valor: 1890, 
    quantidade: 10,
  },
  {
    id: 2, 
    name: 'Monitor Gamer Acer', 
    desc:'Monitor Gamer, 27 Pol. Full HD/Hdmi, Display Port. 165Ghz', 
    imagem:'/imgs/monitores/2.jpg', 
    valor: 1590,
    quantidade: 10,
  }
]

function compra(id) {
  conteudoEmCarrinho()
  if (produtos[id].quantidade == 0) {
    compraNegada();
    return;
  }
  compraPositiva();
  carrinho.value.push({id: id, quantidade: 1});
  produtos[id].quantidade --
}
function removeCompra() {
  produtos.push(carrinho.value.pop());
  if (produtos[id].quantidade == 0) {
    compraNegada();
  }
}

const total = computed((id) => {
  return carrinho.value.length * produtos[0].valor;
});


function conteudoEmCarrinho (id) {
  produtos.forEach((element, index, array) => {
    if (index == id) {
      console.log(element)
      return produtos[id].quantidade++
    }
    return produtos[id]
  })
}


  console.log(conteudoEmCarrinho());


function compraPositiva() {
  $q.notify({
    type: "positive",
    message: "Produto adicionado no carrinho com sucesso!",
  });
}

function compraNegada() {
  $q.notify({
    type: "negativo",
    message:
      "Produto não está disponivel ou encontra-se sem estoque no momento!",
    color: "red",
    type: "warning",
  });
}

</script>

<template>
  <div class="container">
    <div class="botoes-nav">
      <div class="cart">
        <q-icon name="shopping_cart" color="write" style="--fa-animation-duration: 3s;" />
        {{ carrinho.length }}
      </div>
      <p class="total">Total: {{ total }}R$</p>
    </div>
    

  <q-card class="my-card" v-for="produto in produtos" :key="produto.id">
    <q-img :src="produto.imagem" />
    <q-card-section>
      <div class="text-h6">{{ produto.name }}</div>
      <div class="text-subtitle2">{{ produto.desc }}</div>
      <div>{{ produto.valor }}</div> {{ produto.quantidade }}
       <q-btn
            @click="compra(produto.id -1)"
            color="white"
            text-color="black"
            class="btn-comprar"
            label="Comprar"
          />
          <q-btn
            color="white"
            text-color="black"
            @click="removeCompra(produto.id)"
            label="Remover"
          />
    </q-card-section>
    <q-separator dark />
  </q-card>
{{ carrinho }}
  </div>
</template>


<style scoped>
.algo-la {
  display: left;
  align-items: center;
  background-color: black;
}
.my-card {
  width: 100%;
  max-width: 250px;
}
/* .botoes-nav {
  color: rgb(255, 255, 255);
  font-size: 40px;
  display: flex;
  width: 30%;
  float: right;
} */
.cart {
  color: rgb(0, 0, 0);
  font-size: 40px;
  float: right;
  animation-duration: 3s;
}
.total {
  color: rgb(0, 0, 0);
  font-size: 40px;
  float: right;
}
.card {
  display: flex;
  align-items: 5px right;
}
.cardone {
  align-items: 10;
  display: 10px flex;
  width: 100%;
  max-width: 250px;
}

.btns {
  display: flex;
}
</style>
