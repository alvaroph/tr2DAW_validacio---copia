<template>
    <div>
    <h1>Cercador Begudes</h1>

        <button  v-for="item in ['A','B','C','D','E']" @click="seleccionar(item)">
            {{item}}
        </button>
        
    
    </div>
</template>

<script>
    
    export default {
        name: 'CercadorBegudes',
        data() {
            return {
                resultado:[]
            }
        },
        components: {
    
        },
        methods: {
            seleccionar(letter){
                fetch('https://www.thecocktaildb.com/api/json/v1/1/search.php?f=' + letter)
                .then(response => response.json())
                .then(data => {
                    this.resultado = data.drinks;
                    console.log(data);
                });

            }
        },
        computed: {

        },
        mounted() {

        }
        
    }
</script>

<style lang="scss" scoped>

</style>