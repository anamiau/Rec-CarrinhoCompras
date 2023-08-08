<script setup>
import { ref } from 'vue'
 
import MButton from '@/components/MButton.vue'

import { carrinho } from '@/_data/carrinho.js'
const form = ref({
  dados: 'Manu'
})
</script>

<template>
  <div class="container">
    <div class="dadosfinais">
    <!-- <input type="text" v-model="form.dados" >
    <button @click="atualizarDados(form)">Atualizar</button> -->
    <div class="container">
      <h1 class="titulos">Compra finalizada com sucesso!</h1>
      <h2 class="titulos">Confira seus dados:</h2>
      <div class="textos">
        <p class="carrinho-total">Total da compra: R${{ carrinho.total }}</p>
       <p>O nome inserido foi: {{ carrinho.dadosComprador.nome }}</p>
       <p>O email inserido foi: {{ carrinho.dadosComprador.email }}</p>
        <p>A senha inserida foi: {{ carrinho.dadosComprador.senha }}</p>
        <p>A confirmação da senha inserida foi: {{ carrinho.dadosComprador.confirmacao }}</p>
        <p>O endereço inserido foi: {{ carrinho.dadosComprador.endereco }}</p>
        <p>A cidade inserida foi: {{ carrinho.dadosComprador.cidade }}</p>
        <p>O estado inserido foi: {{ carrinho.dadosComprador.estado }}</p>
        <p>A forma de pagamento inserido foi: {{ carrinho.dadosComprador.pagamento }}</p>
        <p>Obs:{{ carrinho.dadosComprador.obs }}</p>
      </div>
   </div> 
  </div>
   <m-button class="butao" texto="Voltar" @click="$router.push({name: 'form'})" />
   <m-button class="butao" texto="Concluir compra" @click="$router.push({name: 'concluirCompra'})"/>
  </div>
</template>

<style scoped>
.container{
  margin-bottom: 10%;
  background-color: rgb(94, 132, 155);
  margin-left: 300px;

}
.textos{
}
.titulos{
}
.butao{

}
</style>