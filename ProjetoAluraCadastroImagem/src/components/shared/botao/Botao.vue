<template>
    <button 
    :class="estiloDoBotao" class="botao" 
    :type="tipo" @click="disparaAcao()">{{ rotulo }}
    </button>
</template>

<script>
export default {


    props: {
        tipo: {
            required: true,
            type: String
        },

        rotulo: {
            required: true,
            type: String
        },

        confirmacao: Boolean,
        estilo: String
    },

    methods: {

        disparaAcao() {

            if (this.confirmacao) {

                if (confirm('Confirma operação? ')) {
                    this.$emit('botaoAtivado');
                }
                return;
            }

            this.$emit('botaoAtivado');
        }
    },
    computed: {
        estiloDoBotao() {
            if (this.estilo == 'padrao' || !this.estilo) return 'botao-padrao';
            if (this.estilo == 'perigo') return 'botao-perigo';
        }
    }
}
</script>

<style>

.botao {
    display: inline-block;
    padding: 5px;
    border-radius: 3px;
    margin: 5px;
    font-size: 1em;
}

.botao-perigo {
    background: firebrick;
    color: white;
}

.botao-padrao {
    background: darkcyan;
    color: white;
}

/*@import './Botao.scss';*/

</style>
