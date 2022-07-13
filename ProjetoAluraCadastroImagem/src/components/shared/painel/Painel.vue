

<template>

  <div class="painel">
    
    <h2 class="painel-titulo" @dblclick="visivel = !visivel">{{ titulo }} </h2>
     
    
    <transition name="painel-fade">
      
      <div class="painel-conteudo" v-show="visivel">
      
        <slot></slot>
        
      </div>
    </transition>
    

  </div>
</template>

<script>
export default {

  props: ['titulo'],

  data() {
    return {
      visivel: true
    }

  }

}
</script>


<style scoped>
/* estilo do painel */

.painel {
  padding: 0 auto;
  border: solid 2px rgb(107, 162, 245);
  display: inline-block;
  margin: 5px;
  box-shadow: 5px 5px 10px rgb(116, 146, 247);
  width: 250px;
  height: 100%;
  vertical-align: top;
  text-align: center;
  background: rgb(121, 172, 253);
  
}

.painel .painel-titulo {
  text-align: center;
  border: solid 3px;
  background: rgb(121, 172, 253);
  margin: 0 0 15px 0;
  padding: 10px;
  text-transform: uppercase;
  

}

* {
  box-shadow: 5px 5px 10px rgb(0, 0, 0);
  
}

.painel-fade-enter, .painel-fade-leave-active {
  opacity: 0;

}

.painel-fade-enter-active, .painel-fade-leave-active {
  transition: opacity .4s;
}

.painel-conteudo {
  overflow: hidden;
}

</style>


<!--Comando no terminal para iniciar projeto: npm run dev -->