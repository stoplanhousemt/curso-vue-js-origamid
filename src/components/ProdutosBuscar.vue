<template>
    <form>
        <input type="text" name="busca" id="busca" placeholder="Buscar..." v-model="query">
        <input type="submit" value="Buscar" id="lupa" @click.prevent="buscarProdutos">
    </form>
</template>

<script>
import router from '@/router'
export default {
    data() {
        return {
            query: ""
        }
    },

    methods: {
        buscarProdutos() {
            this.$router.push({query: {q: this.query}});
        }
    }
}
</script>

<style lang="scss" scoped>
form {
    max-width: 600px;
    margin: 30px auto 60px auto;
    position: relative;
}

#busca {
    width: 100%;
    padding: 20px;
    border: none;
}

#busca:focus,
#busca:hover {
    transform: scale(1.1);
}

#lupa {
    width: 62px;
    height: 62px;
    background: url('../assets/search.svg') no-repeat center center;
    text-indent: -150px;
    border: none;
    cursor: pointer;
    position: absolute;
    top: 0px;
    right: 0px;
    box-shadow: none;

}
</style>