<template>
     <nav>
       <nuxt-link to="/">home</nuxt-link>
       <nuxt-link to="/clientes">clientes</nuxt-link>
       <nuxt-link to="/produtos">produtos</nuxt-link>
      </nav>
</template>
<style scoped>
nav{
  height: 80px;
  width: 100%;
  background-color: grey;
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
}
nav a{
    text-decoration: none;
    font-size: 1.5rem;
    padding: 5px;
    
 
}

</style>