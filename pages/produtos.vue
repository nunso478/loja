<template>
<div class="app">
     <div class="produtos">
        <produto v-for="(artigos,index) in artigo" 
        :key="index" :produto="artigos.produto" 
        :valor="artigos.valor" >
        <button @click="carregaCarrinho(artigos)">comprar</button>
        </produto>
        <!-- <div  class="produto">
           
         </div> -->
    </div>
    <div class="listaCarrinhodeCompras">
        <p>Ultima compra: {{ultimaCompra}}-total- {{total}}</p>
        <div class="produto" v-for="(artigos,index) in carrinhoCompras" 
        :key="index"
       >
            <h2>produtos {{artigos.produto}}</h2>
            <p>{{artigos.valor}} euros</p>
             <button  @click="DescarregaCarrinho()">Eliminar</button>

        </div>

    </div>
</div>
</template>
<script>
export default {
    data (){
        return{
            ultimaCompra:'nenhuma compra efetuada',
            carrinhoCompras:[],
            artigo:[
                {
                    produto:"produto xyz",
                    valor:25
                },
                {
                    produto:"produto xpto",
                    valor:5
                },
                {
                    produto:"produto gto",
                    valor:15
                }
            ]
        }
    },
    methods:{
        carregaCarrinho(artigos){
            this.carrinhoCompras.unshift({...artigos,dataCompra: new Date()});
            this.ultimaCompra = this.carrinhoCompras[0].dataCompra.toString().slice(0,10);      
        },
        DescarregaCarrinho(index){
            this.carrinhoCompras.splice(index,1);

        }
        
    }
}
</script>

<style scoped>
.app{
    display: flex;
    justify-content: around;
}
.listaCarrinhodeCompras{
    display: flex;
    flex-direction: column;
    padding: 10px;
    padding-top: 90px;
    background-color: rgba(48, 88, 48,0.87);
    width: 420px;
    height: 50vh;
    color: rgb(245, 0, 0);
}
.produtos{
    display: flex;
    flex-direction: column;
    height: 98vh;
    align-items: center;
    justify-content: center;

}
.produto{
    background-color: white;
    padding: 3rem;
    margin: 10px;
    width: 480px;
    box-shadow: 0 0 24px rgba(0, 0, 0, 0.3);
}
</style>