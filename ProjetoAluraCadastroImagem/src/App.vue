
<!-- alurapic/src/App.vue -->

<template>
  <div class="corpo">

   <meu-menu :rotas="routes"/>
       <transition name="pagina">
      <router-view></router-view>
      </transition>

  </div>
</template>
<script>

import { routes } from './routes';
import Menu from './components/shared/menu/Menu.vue';

export default {

  components: {
    'meu-menu' : Menu
  },

  data() { 

    return {

      routes: routes.filter(route => route.menu)
    }

  }

}
</script>
<style>
.corpo {
  font-family: Helvetica, sans-serif;
  padding: auto;
  margin: 0 0;
  width: auto;
  height: auto;
  background: rgb(11, 11, 11);
}

.pagina-enter-active, .pagina-leave-active {
  transition: opacity .4s
}

.pagina-enter, .pagina-leave-active {
  opacity: 0
}
</style>


<!--Comando no terminal para iniciar projeto: npm run dev -->