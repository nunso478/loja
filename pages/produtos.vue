<template>
<div>
    <div class="produtos">
         <produto v-for="(artigos,index) in artigo" :key="index" :produto="artigos.produto" :valor="artigos.valor" />
        <!-- <div  class="produto">
             <h2>produtos {{artigos.produto}}</h2>
             <p>{{artigos.valor}} euros</p>
         </div> -->
    </div>
</div>
</template>
<script>
import produto from '../components/produto.vue'
export default {
  components: { produto },
    data (){
        return{
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
    }
}
</script>

<style scoped>
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