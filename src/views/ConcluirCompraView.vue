<script setup>

</script>

<template>
    <h1>DEUU</h1>

    <div class="carrinho">
        <h1 class="title">SEU CARRINHO &#128722;</h1>
        <div class="wrap-carrinho">
            <m-message v-if="carrinho.itens.length === 0" />
            <div v-else>
                <div class="item-carrinho" v-for="(item, index) in carrinho.itens" :key="index">
                    <div class="info-livro">
                        <div class="imagem-livro">
                            <img :src="item.img" class="icon-capa-livro" />
                        </div>
                        <div class="detalhes-livro">
                            <div>
                                <p>{{ item.title }}</p>
                                <p class="info-livro-preco">{{ formatarPreco(item.price) }}/un</p>
                            </div>
                            <div>
                                <p>
                                    Quantidade:
                                    <input type="number" v-model="item.quantidade" @change="atualizaQuantidadeItem(item)"
                                        min="1" />
                                </p>
                                <button @click="removerItemCarrinho(item)">&#128465;</button>
                                <p>Total: {{ formatarPreco(item.total) }}</p>
                            </div>
                        </div>
                    </div>
                </div>
                <m-button @click="limparCarrinho()" texto="Limpar carrinho" />
            </div>
        </div>
        <m-button texto="Voltar" @click="$router.push({ name: 'home' })" />
    </div>
</template>

<style scoped>
.carrinho-total{
color: black;
font-size:x-large;
}
.continuecomp{
background-color: darkgreen;
color: white;
font-size: 1.1rem;
border: 1px solid #ccc;
border-radius: 5px;
padding: 5px 10px;
cursor: pointer;
}
.continuecomp:hover {
background-color: rgb(5, 49, 5)
}
.wrap-carrinho .carrinho-total {
position: fixed;
bottom: 3%;
font-size: 1.5rem;
font-weight: bold;
}


.item-carrinho .info-livro {
display: flex;
margin-bottom: 10px;
}
.detalhes-livro {
display: flex;
flex-direction: column;
width: 100%;
}
.detalhes-livro p {
margin: 0;
}
.detalhes-livro div {
display: flex;
justify-content: space-between;
width: 100%;
}


.detalhes-livro input[type='number'] {
width: 50px;
text-align: center;
border: none;
border-bottom: 1px solid black;
background-color: transparent;
margin-left: 10px;
}


.detalhes-livro button {
background-color: transparent;
border: none;
cursor: pointer;
font-size: 1.5rem;
color: black;
padding: 0;
margin: 0;
}


.info-livro-preco {
margin-left: auto;
}
.icon-capa-livro {
width: 30px;
margin-right: 10px;
}
.container-geral {
display: grid;
grid-template-columns: 3fr 1fr;
}


.carrinho {
min-width: 20%;
margin-bottom: 100%;
background-color: white;
}
.listagem-livros {
display: flex;
flex-wrap: wrap;
}
.title{
color: rgb(0, 0, 0);
}



</style>